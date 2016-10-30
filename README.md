package mypack;

public class FixedStack implements Stack{
	  private int stck[];
	  private int tos;
	  FixedStack(int size) {
		    stck = new int[size];
		    tos = -1;
}
	  
	  public void push(int item) {
		    if(tos==stck.length-1) // use length member 
		      System.out.println("Stack is full.");
		    else 
		      stck[++tos] = item;
		  }

		  // Pop an item from the stack
		  public int pop() {
		    if(tos < 0) {
		      System.out.println("Stack underflow.");
		      return 0;
		    }
		    else 
		      return stck[tos--];
		  }
		}
    ------------------------------
    package mypack;

class Ifstack
{ public static void main(String args[]) { 
	Stack mystack;
	VariableStack ds = new VariableStack(5); 
	FixedStack fs = new FixedStack(8);
mystack = ds; 
  for(int i=0; i<12; i++)
	  mystack.push(i);
mystack = fs; 
 for(int i=0; i<8; i++)
	 mystack.push(i);
mystack = ds;
System.out.println("Values in dynamic stack:"); 
for(int i=0; i<12; i++)
	System.out.println(mystack.pop());
mystack = fs;
System.out.println("Values in fixed stack:");
for(int i=0; i<8; i++)
	System.out.println(mystack.pop());
}
} 
---------------
package mypack;

interface Stack {
	void push(int item);
 int pop(); 
}
----------------------------
package mypack;

class VariableStack implements Stack {
	  private int stck[];
	  private int tos;
	  
	  VariableStack(int size) {
	    stck = new int[size];
	    tos = -1;
	  }
	  public void push(int item) {
	    // if stack is full, allocate a larger stack
	    if(tos==stck.length-1) {
	      int temp[] = new int[stck.length * 2]; // double size
	      for(int i=0; i<stck.length; i++) temp[i] = stck[i];
	      stck = temp;
	      stck[++tos] = item;
	    }
	    else 
	      stck[++tos] = item;
	  }

	  // Pop an item from the stack
	  public int pop() {
	    if(tos < 0) {
	      System.out.println("Stack underflow.");
	      return 0;
	    }
	    else 
	      return stck[tos--];
	  }
	}
  -------------------------------
  package mypack;



class Main {
	  public static void main(String args[]) {
	    FixedStack mystack1 = new FixedStack(7);
	    FixedStack mystack2 = new FixedStack(8);

	    // push some numbers onto the stack
	    for(int i=0; i<12; i++) mystack1.push(i);
	    for(int i=0; i<8; i++) mystack2.push(i);

	    // pop those numbers off the stack
	    System.out.println("Stack in mystack1:");
	    for(int i=0; i<5; i++) 
	       System.out.println(mystack1.pop());

	    System.out.println("Stack in mystack2:");
	    for(int i=0; i<8; i++) 
	       System.out.println(mystack2.pop());
	  }
}
------------------------------
package mypack;
	
	class Main1 {
		public static void main(String args[]) {
			VariableStack mystack = new VariableStack(5);
			VariableStack mystack3 = new VariableStack(8);
	
	 for(int i=0; i<12; i++)
		 mystack.push(i);
	 for(int i=0; i<20; i++) 
		 mystack3.push(i);
	System.out.println("Stack in mystack:");
	for(int i=0; i<12; i++)
		System.out.println(mystack.pop());
	System.out.println("Stack in mystack2:");

}
}
	
	
	
	-----------------
  Stack is full.
Stack is full.
Stack is full.
Stack is full.
Stack is full.
Stack in mystack1:
6
5
4
3
2
Stack in mystack2:
7
6
5
4
3
2
1
0
