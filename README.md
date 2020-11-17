# COL-106
// Implements Dictionary using Doubly Linked List (DLL)
// Implement the following functions using the specifications provided in the class List

public class A1List extends List {

    private A1List  next; // Next Node
    private A1List prev;  // Previous Node 

    public A1List(int address, int size, int key) { 
        super(address, size, key);
    }
    
    public A1List(){
        super(-1,-1,-1);
        // This acts as a head Sentinel

        A1List tailSentinel = new A1List(-1,-1,-1); // Intiate the tail sentinel
        
        this.next = tailSentinel;
        tailSentinel.prev = this;
    }

    public A1List Insert(int address, int size, int key)
    {
        A1List node = new A1list(adddress,size,key);
       if(A1List.key!=-1){
        node.prev=(-1,-1,-1);
        return node;
        }
        return null;
    }

    public boolean Delete(Dictionary d) 
    {
        While(this.prev!=(-1,-1,-1)){
          If(this.key==d.key && this.size==d.size){
              this.prev.next=this.next;
             this.next.prev=this.prev;
             return true;
           }
          else this=this.prev;
        while(this.next!=tailSentinel ){
           if(this.key==d.key && this.size==d.size){
              this.prev.next=this.next;
             this.next.prev=this.prev;
             return true;
           }
          else this=this.next;
        return false;
    }

    public A1List Find(int k, boolean exact)
    { 
      if(exact==true){
        while(this.prev!=(-1,-1,-1)){
          if(this.key=k){
             return this;
           }
        else this=this.prev;
        }
        while(this.next!=(-1,-1,-1)){
          if(this.key=k){
             return this;
           }
        else this=this.next;
        }
       }
       else if(exact==false){
         while(this.prev!=(-1,-1,-1)){
          if(this.key>=k){
             return this;
           }
        else this=this.prev;
        }
        while(this.next!=(-1,-1,-1)){
          if(this.key>=k){
             return this;
           }
        else this=this.next;
        }
        return null;
    }

    public A1List getFirst()
    {
      if(!((this.prev==null && this.next==tailSentinel)  &&( this.next==null && this.prev==(-1,-1,-1)))){
        while(this.prev!=(-1,-1,-1)){
            this =this.prev;
        }
        return this;
        }
        return null;
    }
    
    public A1List getNext() 
    { 
        if(this.next!=tailSentinel){
           return this.next;
         }
        return null;
    }

    public boolean sanity()
    {
        if(this.next.prev!=this)
           return false;
        if(tailSentinel.next!=null)
           return false;
        return true;
    }

}


