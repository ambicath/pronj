# pronj
public class JavaSpiralDemo{
	public static void main(String args[]){
		if(args.length >= 2){
			int x = Integer.parseInt(args[0]);
			int y = Integer.parseInt(args[1]);
			int length = x*y;
			int oplen=0;
			String output="";
			int k = 2;

			String[][] string2Arr = new String[x][y];
			x-=1;
			y-=1;

			for (int i = 0; i <=x; i++)
   				for (int j = 0; j <= y; j++){
					try{
						string2Arr[i][j] = args[k];
					}
					catch (ArrayIndexOutOfBoundsException ae){
						System.out.println("Not enough values supplied. Needed: " + (length+2) + ", Provided: " + args.length);
						System.out.println("Null values supplied");
					}
					k++;
				}

			int s=0;
			int t=0;
			int z=0;
			int xc=0;
			int yc=0;

			while(oplen<length){
				if(z%2==0){
					for(;  t<=y; t++){
						output = output + "" + string2Arr[s][t];
						oplen++;
					}
					s+=1;
					t=y;
					for(; s<=x; s++){
						output = output + "" + string2Arr[s][t];
						oplen++;
					}
					s-=1;
					xc+=1;
					y-=1;
					t-=1;
					z++;
				}
				else{
					for(; t>=yc; t--){
						output = output + "" + string2Arr[s][t];
						oplen++;
					}
					s-=1;
					t+=1;
					for(; s>=xc; s--){
						output = output + "" + string2Arr[s][t];
						oplen++;
					}
					s+=1;
					yc+=1;
					x-=1;
					t+=1;
					z++;
				}
			}

			System.out.println("Output: " + output);
		}
		else{
			System.out.println("Please provide commandline inputs");
		}
	}
}
