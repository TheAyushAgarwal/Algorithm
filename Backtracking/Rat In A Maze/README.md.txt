```java

class RatInAmaze{
    boolean call(int[][]arr,boolean[][] vis,int a,int b, int c,int d){
        if(a==c && b==d){
            return true;
        }
        vis[a][b]=true;
        if((b+1)<arr.length && !vis[a][b+1] && arr[a][b+1]==1){
            boolean k=call(arr,vis,a,b+1,c,d);
            if(k==true){
                return true;
            }
        }
        if((a+1)<arr.length && !vis[a+1][b] && arr[a+1][b]==1){
            boolean k=call(arr,vis,a+1,b,c,d);
            if(k==true){
                return true;
            }
        }
        if((a-1)>=0 && !vis[a-1][b] && arr[a-1][b]==1){
            boolean k=call(arr,vis,a-1,b,c,d);
            if(k==true){
                return true;
            }
        }
        if((b-1)>=0 && !vis[a][b-1] && arr[a][b-1]==1){
            boolean k=call(arr,vis,a,b-1,c,d);
            if(k==true){
                return true;
            }
        }
        return false;
    }
    public static void main(String args[]){
        int arr[][]={{1,0,0,0},{1,1,0,0},{0,1,1,0},{0,0,1,1}};
        boolean vis[][]=new boolean[arr.length][arr.length];
        RatInAmaze r=new RatInAmaze();

        // starting vertex
        int a=0;
        int b=0;

        // destination Vertex
        int c=3;
        int d=3;
        System.out.println("path= "+r.call(arr,vis,a,b,c,d));
    }
}


```