# LinkedList
public class Linkedlist
{
    private ListNode firstNode;
    private ListNode lastNode;
    private ListNode current;

    public Linkedlist ()
    {
      firstNode =lastNode = null;
    }


    public void insertAtFront(Object insertitem)
    {
      if ( isEmpty())
        firstNode = lastNode = new ListNode(insertitem);
      else
        firstNode = new ListNode (insertitem,firstNode);
    }

    public void insertAtBack(Object insertItem)
    {
      if ( isEmpty())
       firstNode = lastNode = new ListNode(insertItem);
      else
       lastNode = lastNode.next = new ListNode(insertItem);
   
    }



    public Object removeFromFront() throws EmptyListException
    {
    
      Object removeItem = null;

      if(isEmpty())
        {  throw new EmptyListException(); }
        
           removeItem = firstNode.data;

      if(firstNode.equals(lastNode)) 
         firstNode = lastNode = null;

      else
        firstNode = firstNode.next;
        
      return removeItem;
        
    }

    public Object removeFromBack() throws EmptyListException
    {
        Object removeltem = null;

        if (isEmpty())
            throw new EmptyListException();

        removeltem = lastNode.data;
        
        if (firstNode.equals(lastNode)) 
            firstNode = lastNode = null;

        else
        {   current = firstNode;
       
            while (current.next != lastNode) 
            {      current = current.next;}

            lastNode = current;
            current.next = null;
        }
        return removeltem;

        
    }
    
    public boolean isEmpty()
    {
      return firstNode == null;
    }



    public void print()
    {

      if(isEmpty())
      {
        System.out.println("Empty list ");
        return ;
      }

      System.out.println ("The list is :");
      current = firstNode;

      while (current!= null)
      {
        System.out.print (current.data.toString()+"  ");
        current = current.next;
      }

      System.out.println ("\n");

    }


    public Object getFirst()
    {
      if (isEmpty())
      return null;

      else 
      {

      current = firstNode;
      return current.data;
      }
    }

    public Object getNext()
    {
      if(current != lastNode)
      {
        current = current.next;
        return current.data;
      }
      else
      { return null;}
     
    }
}

