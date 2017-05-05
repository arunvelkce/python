import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.io.InputStreamReader;
public class Visitors{
	public static void main(String[] args)throws Exception
	{	
		BufferedReader br=new BufferedReader(new FileReader("visitor.txt"));		
		int i,j,k,sum,repeat,count=0;
		int month,month1,hour,date,date1,monthStart,monthStart1,monthEnd,monthEnd1,dayStart,dayStart1,dayEnd,dayEnd1,timeStart,timeEnd;
		int visitor[][][];
	visitor=new int[12][][];
	int days[]={31,29,31,30,31,30,31,31,30,31,30,31};
	for(i=0;i<12;i++){
		visitor[i]=new int[days[i]][24];
					}
	for(i=0;i < visitor.length;i++){
		for(j=0;j < visitor[i].length;j++){
			for(k=0;k < visitor[i][j].length;k++){
			visitor[i][j][k]=Integer.valueOf(br.readLine());
												 }
											}
									}
	      BufferedReader  brN=new BufferedReader(new InputStreamReader(System.in)); 
	      do
	      {
        System.out.println("choose the option from the below list to perform the specific operation.....:");
        System.out.println("1.particular month\n2.particular day\n3.particular hour\n4.month boundry\n5.month and day boundry\n6.month day and hour boundry\n7.multiple month boundry\n8.month and multiple day boundry\n9.month,day and multiple hour boundry\n10.multiple month day hour boundary");
       
		int option=Integer.valueOf(brN.readLine());



		System.out.println("enter the option");
		switch(option)
			{

//month case 1
			case(1):
				{
					System.out.println("enter the month(from 1 - 12) to find the average and sum of visitors:");
					month=Integer.valueOf(brN.readLine());
					month1=month-1;
					i=month1;
					sum=0;
					for(j=0;j<visitor[i].length;j++){
						for(k=0;k<visitor[i][j].length;k++){
							sum+=visitor[i][j][k];
															}
													}
					System.out.println("sum of "+month+" is "+sum);
					System.out.println("the Average of "+month+" is "+  sum/days[month]);
					break;
				}

	//days case2 
			case(2):
				{
					System.out.println("enter the date(from 1 - 31 to find the average and sum of visitors:");
					date=Integer.valueOf(brN.readLine());
					date1=date-1;
					sum=0;
					for(i=0;i<visitor.length;i++){
						for(j=0;j<visitor[i].length;j++){
							for(k=0;k<visitor[i][j].length;k++){
								if(j==date1){
									count++;
										sum+=visitor[i][j][k];
											}
																}
														}
													}
					System.out.println("sum of "+date+" is "+sum);
					System.out.println("the Average of "+date+" is "+  sum/count);
					break;
				}

//hour case 3
			case(3):
				{
					count=0;
					System.out.println("enter the hour(from 0-23) to find the average and sum of visitors:");
					hour=Integer.valueOf(brN.readLine());
					k=hour;
					sum=0;
					for(i=0;i<visitor.length;i++){
						for(j=0;j<visitor[i].length;j++){
							sum+=visitor[i][j][k];
							count++;
														}
												}
					System.out.println("sum of "+hour+" is "+sum);
					System.out.println("the Average of "+hour+" is "+  sum/count);
					break;
				}

	//case 4 boundary of  months
			case(4):
				{
					count=0;
					System.out.println("enter the month range(from 1 - 12) to find the average and sum of visitors:");
					System.out.print("starting month ");
					monthStart=Integer.valueOf(brN.readLine());
					monthStart1=monthStart-1;
					System.out.print("ending month ");
					monthEnd=Integer.valueOf(brN.readLine());
					monthEnd1=monthEnd-1;
					sum=0;
					for(i=monthStart1;i<=monthEnd1;i++){
						for(j=0;j<visitor[i].length;j++){
							for(k=0;k<visitor[i][j].length;k++){
								count++;
								sum+=visitor[i][j][k];
																}
														}
																}
					System.out.println("sum from "+monthStart+" to "+monthEnd+" id "+sum);
					System.out.println(" average from "+monthStart+" to "+monthEnd+" is "+sum/count);
					break;
				}

// case 5 day month and boundary 
			case(5):
				{
					count=0;
					System.out.println("enter the month range and day to find the average and sum of visitors:");
					System.out.print("starting month ");
					monthStart=Integer.valueOf(brN.readLine());
					monthStart1=monthStart-1;
					System.out.print("ending month ");
					monthEnd=Integer.valueOf(brN.readLine());
					monthEnd1=monthEnd-1;
					System.out.print("starting day ");
					dayStart=Integer.valueOf(brN.readLine());
					dayStart1=dayStart-1;
					System.out.print("ending day ");
					dayEnd=Integer.valueOf(brN.readLine());
					dayEnd1=dayEnd-1;
					sum=0;
					for(i=monthStart1;i<=monthEnd1;i++){
						for(j=0;j<visitor[i].length;j++){
							if((j>=dayStart1)&&(j<=dayEnd1)){
								for(k=0;k<visitor[i][j].length;k++){
									count++;
										sum+=visitor[i][j][k];
																	}
															}
														}
														}
					System.out.print("sum from the boundary of month "+monthStart+" to "+monthEnd);
					System.out.println(" in the date from "+dayStart+" to "+dayEnd+" is "+sum);
					System.out.println(" average from "+dayStart+" to "+dayEnd+" is "+sum/count);
					break;
				}

//case 6  month day hour boundary:
			case(6):
				{
					count=0;
					System.out.println("enter the month range,day range and hour range to find the average and sum of visitors:");
					System.out.print("starting month ");
					monthStart=Integer.valueOf(brN.readLine());
					monthStart1=monthStart-1;
					System.out.print("ending month ");
					monthEnd=Integer.valueOf(brN.readLine());
					monthEnd1=monthEnd-1;
					System.out.print("starting day ");
					dayStart=Integer.valueOf(brN.readLine());
					dayStart1=dayStart-1;
					System.out.print("ending day ");
					dayEnd=Integer.valueOf(brN.readLine());
					dayEnd1=dayEnd-1;
					System.out.print("starting time ");
					timeStart=Integer.valueOf(brN.readLine());
					System.out.print("ending time ");
					timeEnd=Integer.valueOf(brN.readLine());
					sum=0;
					for(i=monthStart1;i<=monthEnd1;i++){
						for(j=0;j<visitor[i].length;j++){
							if((j>=dayStart)&&(j<=dayEnd)){
								for(k=timeStart;k<timeEnd;k++){
									count++;
									sum+=visitor[i][j][k];
																}
															}
														 }
														}
					System.out.print("sum from the boundary of month "+monthStart+" to "+monthEnd);
					System.out.print(" in the date from "+dayStart+" to "+dayEnd);
					System.out.print(" in the time from "+timeStart+" to "+timeEnd+" is "+sum);
					System.out.print("average from the boundary of month "+monthStart+" to "+monthEnd);
					System.out.print(" in the date from "+dayStart+" to "+dayEnd);
					System.out.print(" in the time from "+timeStart+" to "+timeEnd+" is "+sum/count);
					break;
				}
	//case 7 multiple  month boundaries
			case(7):
				{
					sum=0;
					count=0;
					int choice;
					System.out.println("enter the month range(from 1 - 12) to find the average and sum of visitors:");
						do{
							System.out.println("enter the month range(from 1 - 12) to find the average and sum of visitors:");
							System.out.print("starting month ");
 							monthStart=Integer.valueOf(brN.readLine());
							monthStart1=monthStart-1;
							System.out.print("ending month ");
 							monthEnd=Integer.valueOf(brN.readLine());
 							monthEnd1=monthEnd-1;
							for(i=monthStart1;i<=monthEnd1;i++){
								for(j=0;j<visitor[i].length;j++){
									for(k=0;k<visitor[i][j].length;k++){
										count++;
										sum+=visitor[i][j][k];
																		}
																}
																}
						System.out.println("press 0 for exit");
						choice=Integer.valueOf(brN.readLine());
						}while(choice>1);
					System.out.println("sum from "+monthStart+" to "+monthEnd+" id "+sum);
					System.out.println(" average from "+monthStart+" to "+monthEnd+" is "+sum/count);
					break;
				}

//case 8 constant month wuth different days
			case(8):
				{
					count=0;
					System.out.println("enter the month range(from 1 - 12):");
					System.out.print("starting month ");
					monthStart=Integer.valueOf(brN.readLine());
					monthStart1=monthStart-1;
					System.out.print("ending month ");
					monthEnd=Integer.valueOf(brN.readLine());
					monthEnd1=monthEnd-1;
					sum=0;
					int choice1;
						do{
							System.out.println("enter the date range(from 1 - 31):");
							System.out.print("starting day ");
							dayStart=Integer.valueOf(brN.readLine());
							dayStart1=dayStart-1;
							System.out.print("ending day ");
							dayEnd=Integer.valueOf(brN.readLine());
							dayEnd1=dayEnd-1;
							for(i=monthStart1;i<=monthEnd1;i++){
								for(j=0;j<visitor[i].length;j++){
									if((j>=dayStart)&&(j<=dayEnd)){
										for(k=0;k<visitor[i][j].length;k++){
											count++;
											sum+=visitor[i][j][k];
																			}
																	}
																	}
																}
						System.out.println("press 0 for exit");
						choice1=Integer.valueOf(brN.readLine());
						}while(choice1>0);
					System.out.println("sum from is  "+sum);
					System.out.println(" average  is "+sum/12);
					break;
				}

//choice  9 month cons days cons date differ
			case(9):
				{
					count=0;
					System.out.println("enter the month range(from 1 - 12):");
					System.out.print("starting month ");
					monthStart=Integer.valueOf(brN.readLine());
					monthStart1=monthStart-1;
					System.out.print("ending month ");
					monthEnd=Integer.valueOf(brN.readLine());
					monthEnd1=monthEnd-1;
					System.out.println("enter the date range(from 1 - 31):");
					System.out.print("starting day ");
					dayStart=Integer.valueOf(brN.readLine());
  					dayStart1=dayStart-1;
					System.out.print("ending day ");
					dayEnd=Integer.valueOf(brN.readLine());
					dayEnd1=dayEnd-1;
				    sum=0;
					int choice2;
					do{
							System.out.println("enter the hour range(from 0-23):");
							System.out.print("starting time ");
							timeStart=Integer.valueOf(brN.readLine());
							System.out.print("ending time ");
							timeEnd=Integer.valueOf(brN.readLine());
							for(i=monthStart1;i<=monthEnd1;i++){
								for(j=0;j<visitor[i].length;j++){
									if((j>=dayStart1)&&(j<=dayEnd1)){
										for(k=timeStart;k<timeEnd;k++){
												count++;
												sum+=visitor[i][j][k];
																	}
																		}
														}
													}
							System.out.println("press 0 for exit");
							choice2=Integer.valueOf(brN.readLine());
						}while(choice2>0);
						System.out.println("sum from  the input boundaries is "+sum);
						System.out.println(" average of input boundaries is  "+sum/12);
							break;
				}

//case 10 multiple intervals
		case(10):
				{
					count=0;
					System.out.println("enter the month range(from 1 - 12):");
					sum=0;
					int choice3;
						do{
							System.out.print("starting month ");
							monthStart=Integer.valueOf(brN.readLine());
							monthStart1=monthStart-1;
							System.out.print("ending month ");
							monthEnd=Integer.valueOf(brN.readLine());
							monthEnd1=monthEnd-1;
							System.out.println("enter the date range(from 1 - 31):");
							System.out.print("starting day ");
							dayStart=Integer.valueOf(brN.readLine());
							dayStart1=dayStart-1;
							System.out.print("ending day ");
							dayEnd=Integer.valueOf(brN.readLine());
							dayEnd1=dayEnd-1;
							System.out.println("enter the hour range(from 0 - 23):");
							System.out.print("starting time ");
							timeStart=Integer.valueOf(brN.readLine());
							System.out.print("ending time ");
							timeEnd=Integer.valueOf(brN.readLine());
							for(i=monthStart1;i<=monthEnd1;i++){
								for(j=0;j<visitor[i].length;j++){
									if((j>=dayStart1)&&(j<=dayEnd1)){
										for(k=timeStart;k<timeEnd;k++){
												sum+=visitor[i][j][k];
												count++;
																	}
																}
												}
								}
				System.out.println("press 0 for exit");
				choice3=Integer.valueOf(brN.readLine());
					}while(choice3>0);
				System.out.println("sum from the given input is "+sum);
				System.out.println(" average from the given input is "+sum/count);
				break;
				}
						}
				System.out.println("press 0 to exit  from the program");
				repeat=Integer.valueOf(brN.readLine());
     			 }while(repeat>0);

		}
		}
