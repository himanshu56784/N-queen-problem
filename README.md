class Queen
{
	static void display(int x[][])
	{
		for(int i[]:x)
		{
			for(int j:i)
			{
				System.out.print(j+" ");
			}
			System.out.println();
		}
	}
	static boolean isValid(int x[][],int row,int col)
	{
	int i,j;
	for(i=col;i>=0;i--)
	{
	if(x[row][i]==1)return false;	
	}
	for(j=row;j>=0;j--)
	{
	if(x[j][col]==1)return false;	
	}	
	for(i=row,j=col;j>=0 && i>=0;j--,i--)
	{
	if(x[i][j]==1)return false;	
	}	
	for(i=row,j=col;i>=0 && j<4 ;j++,i--)
	{
	if(x[i][j]==1)return false;	
	}	
	return true;	
	}
	static boolean check(int x[][],int r)
	{
		if(r>=4)return true;
		for(int i=0;i<4;i++)
		{
		if(isValid(x,i,r))
		{
			x[i][r]=1;
			if(check(x,r+1))return true;
			x[i][r]=0;
		}			
		
	}	
	return false;	
	}
	public static void main(String ar[])
	{
	int[][] x=new int[4][4];
	check(x,0);
	display(x); 
	}
}
