# implementation-of-linked-list
llinked list implementation
import java.io.*;
class LinkedList
{
    private class Node 
    {
        char data;
        Node next;
    }
    private Node head;
    private Node tail;//by adding this to at the end of LinkedList we can many fucnction O(1)
    private int size;
   public void display()
    {
        Node temp=this.head;
         if(this.size==0)
         {
             System.out.println("no elements");
         }
        while(temp!=null)
        {
            System.out.print(temp.data+", ");
            temp=temp.next;
        }
        System.out.println(" ");
    }
    public void addlast(char item)
    {
        Node nn=new Node();
        nn.data=item;
        nn.next=null;
        if(this.size>=1)
        {
            this.tail.next=nn;
        }
        if(this.size==0)
        {
            this.head=nn;
            this.tail=nn;
            this.size++;
        }
        else
        {
           this.tail=nn;
            this.size++;
        }
        
    }
    public void addfirst(char item)
    {
        Node nn=new Node();
        nn.data=item;
        nn.next=null;
        if(this.size==0)
        {
            this.head=nn;
            this.size++;
            this.tail=nn;
        }
        else 
        {
            Node temp=head;
            nn.next=head;
            head=nn;
            size++;
        }
    }
    private Node getat(int index)//returninig node at that position
                                //LinkedList$Node@232204a1
    {
        Node temp=head;
        if(size==0)
        {
            System.out.println("no elemnts");
            
        }
        else
        {
            for(int i=0;i<=index;i++)
            {
                temp=temp.next;
            }
        }
        return temp;
    }
    public void getlast()
    {
        if(size==0)
        {
            System.out.println("no elemnts");
        }
        else
        {
            System.out.println(tail.data);
        }
    }
     public void getfirst()
    {
        if(size==0)
        {
            System.out.println("no elemnts");
        }
        else
        {
            System.out.println(head.data);
        }
    }
    public char getatposition(int index)
    {
              Node temp=head;
        if(index<0||index>size-1)
        {
            System.out.println("invalid index");
        }
         
  
        else
        {
               
            for(int i=0;i<index-1;i++)
            {
                temp=temp.next;
            }
            
        }
      return temp.data;
    }
    public char removedfirst()
    {
        Node temp=head;
        if(size==0)
        {
            
            System.out.println("linked list empty");
        }
        char rev=head.data;
        if(size==1)
        {
           head=null;
            tail=null;
            size--;
        }
        else
        {
            head=temp.next;
        }
        return rev;
    }
     public char removeat(int index)
     {
         Node temp=head;
         if(size==0)
         {
             System.out.println("no elemnts to remove");
         }
         else
         {
          for(int i=1;i<index-1;i++)
          {
              temp=temp.next;
          }
         }
         temp.next=temp.next.next;
         return temp.data;
     }
    
    
    public static void main (String[] args) 
    {
        LinkedList ll=new LinkedList();
      ll.addlast('a') ;
      ll.addlast('k');
      ll.addlast('l');
      ll.addlast('m');
      ll.addlast('h');
        ll.display();
        System.out.println("................");
      //System.out.println(ll.getat(2)); 
     // ll.getlast();
     // ll.getfirst();
     // System.out.println(ll.getatposition(0));
       //System.out.println(ll.removedfirst()); 
      //System.out.println(ll.removedfirst()); 
        //System.out.println(ll.removedfirst()); 
         //ll.display();
        System.out.println(ll.removeat(2));
        ll.display();
    }
}
