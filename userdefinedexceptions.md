<h1>user defined exceptions</h1>

<h2>java:</h2>
<i><b>key words:
-try
-catch
-throw
-throws
-finally
</b></i>
<div>import java.util.Scanner;
import java.util.Random;
class outOfRangeException extends Exception{    //defining a user defined exception
  public String msg;
  public outOfRangeException(String s){
    this.msg=s;
  }
}
public class Main {
  private static int range=50;
  public static void main(String[] args) {
    Random r=new Random();
    int guess=r.nextInt(range);
    //System.out.println(guess);
    System.out.println("guess a number between 0 and"+range);
    Scanner sc=new Scanner(System.in);
    try{
      int n=sc.nextInt();
      if(n<0 || n>range){
        throw new outOfRangeException("exception occoured\ninput not in range...try next time");}
      else{
        if(n==guess)
      System.out.println("you are right\nwelldone");
      else{
        System.out.println("sorry...wrong guess\nthe answer is"+guess);
      }
      }
    }
    catch(outOfRangeException e){
      System.out.println(e.msg);
    }
    catch(Exception e){
      System.out.println("exception occoured\n"+e);
    }
    finally{
      System.out.println("thank you");
    }
      }
  }</div>

<h2>equivalent code in python:</h2>
<i><b>key words:
-try
-except
-else
-raise
-finally
</b></i>
<div>import random
class myexception(Exception):   #defining a user defined exception
  def __init__(self,n,msg):
    self.msg=msg
    #print(n,'not in specified range')
print('guess any number between 0&50')
i=random.randint(0,51)
try:
  inp=int(input())
  if inp>50 or inp<0:
    raise myexception(inp,'{} not  in specified range'.format(inp))
except myexception as e:
  print('exception raised:',e.msg)
except Exception as e:
  print('exception raised in the way')
  print(e)
else:
  if inp==i:
    print('well done')
  else:
    print('wrong guess')
finally:
  print('hidden number is',i,'\nthank you...')
                      </div>
