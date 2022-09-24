# deletemidlinked
import java.util.*;
import java.lang.*;
import java.io.*;

public class Main
{
	public static void main (String[] args) throws java.lang.Exception
	{
		//your code here
                Scanner sc=new Scanner(System.in);
                int n=sc.nextInt();
                ll l1=new ll();
                for(int i=0;i<n;i++){
                        l1.insertatlast(sc.nextInt());
                }
                l1.deletemid();
                l1.print();
	}
}
class ll{
        Node head;
        void insertatlast(int data){
                Node newnode=new Node(data);
                if(head==null){
                        head=newnode;
                        return;
                }
                Node temp=head;
                while(temp.next!=null){
                        temp=temp.next;
                }
                temp.next=newnode;
                
        }
        void deletemid(){
                Node slow=head;
                Node fast=head;
                Node prev=null;
                if(head.next==null){
                        head.data=-1;
                        return;
                }
                while(fast!=null && fast.next!=null){
                        fast=fast.next.next;
                        prev=slow;
                        slow=slow.next;
                }
                prev.next=slow.next;
                return;
        }
           void print(){
                Node temp=head;
                while(temp!=null){
                        System.out.print(temp.data+" ");
                        temp=temp.next;
                        
                }
        }
}
class Node{
        int data;
        Node next;
        Node(int data){
                this.data=data;
                this.next=null;
        }
}
