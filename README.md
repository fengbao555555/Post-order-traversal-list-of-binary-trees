# Post-order-traversal-list-of-binary-trees
 
 code as followed:
 # public class Solution {
    public boolean VerifySquenceOfBST(int [] sequence) {
        int index=sequence.length-1;
        if(sequence==null||sequence.length==0)
        {
            return false;
        }
        return laterorder(sequence,sequence[index],index);
    }
    private boolean laterorder(int [] a, int root,int index){
        int mid=0;
        for(int i=0;i<index;i++){
            if(a[i]<root){
                mid++;
            }
            else 
                break;
        }
        int cou=mid;
        for(int j=mid;j<index;j++){
            if(a[j]>root){
                cou++;
            }
            else
                return false;
        }
        if(cou==index){
                return true;
            } 
        return laterorder(a,a[mid-1],mid-1)&&laterorder(a,a[index-1],index-1);
        }

    }
