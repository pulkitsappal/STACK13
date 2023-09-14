echo "******************* Welcome to STACK 13 *****************************"

deck=(1 2 3 4 5 6 7 8 9 10 11 12 13 1 2 3 4 5 6 7 8 9 10 11 12 13 1 2 3 4 5 6 7 8 9 10 11 12 13 1 2 3 4 5 6 7 8 9 10 11 12 13)

#Distributing Cards
deck=( $(shuf -e "${deck[@]}") )
	
for i in 0 1 2 3 4 5 6 7 8 9 10 11 12 
do
	computer+=(${deck[$i]})	
	user+=(${deck[$i+13]})
done

for i in 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
do
	unset deck[$i]
done




#Displaying Cards

echo "Computer Cards : "
for i in 0 1 2 3 4 5 6 7 8 9 10 11 12 
do
	if [ ${computer[$i]} -eq 1 ]
	then
		echo "A"
	elif [ ${computer[$i]} -eq 11 ]
	then
		echo "J"
	elif [ ${computer[$i]} -eq 12 ]
	then
		echo "Q"
	elif [ ${computer[$i]} -eq 13 ]
	then
		echo "K"
	else
		echo ${computer[$i]}
	fi
done

echo "User Cards : "
for i in 0 1 2 3 4 5 6 7 8 9 10 11 12 
do
	if [ ${user[$i]} -eq 1 ]
	then
		echo "A"
	elif [ ${user[$i]} -eq 11 ]
	then
		echo "J"
	elif [ ${user[$i]} -eq 12 ]
	then
		echo "Q"
	elif [ ${user[$i]} -eq 13 ]
	then
		echo "K"
	else
		echo ${user[$i]}
	fi
done



#Game Starts

user_win=0
computer_win=0

while [ $user_win -eq 0 -a $computer_win -eq 0 ]
do
	
	#Computer's Turn
	sum=0

	#Adding Computer's Cards
	for i in 0 1 2 3 4 5 6 7 8 9 10 11 12
	do 
		sum+=${computer[$i]}
	done


	#Checking Computer's Winnings.............	
	if [ $sum -eq 91 ]{
	then
		echo "Computer Win's"
		computer_win=1
        break

	#Sum not equals to 91	
	
	else
		echo "Computer's Turn"
		deck=( $(shuf -e "${deck[@]}") )
		
		for i in 0 1 2 3 4 5 6 7 8 9 10 11 12
		do
			sum-=${computer[$i]}
			sum+=${deck[26]}
			
			
			if [ $sum -eq 91 ]
			then
				temp=${computer[$i]}
				computer[$i]=${deck[26]}
				deck[26]=$temp
				

				computer_win=1
				echo "Computer Wins........."
            
                break
			fi
			
		    sum+=${computer[$i]}
			sum-=${deck[26]}
    
              
		done
		        
	fi
	
	echo "Computer Cards : "
	for i in 0 1 2 3 4 5 6 7 8 9 10 11 12 
		do
			if [ ${computer[$i]} -eq 1 ]
			then
				echo "A"
			elif [ ${computer[$i]} -eq 11 ]
			then
				echo "J"
			elif [ ${computer[$i]} -eq 12 ]
			then
				echo "Q"
			elif [ ${computer[$i]} -eq 13 ]
			then
				echo "K"
			else
				echo ${computer[$i]}
			fi
		done

	
	sum=0

	#User's Turn

	#Adding User's Cards
	for i in 0 1 2 3 4 5 6 7 8 9 10 11 12
	do 
		sum+=${user[$i]}
	done


	#Checking User's Winnings........	
	if [ $sum -eq 91 ]
	then
		echo "You Win........."
		user_win=1
        break

	#Sum not equals to 91	
	else
		echo "Your Turn"
		deck=( $(shuf -e "${deck[@]}") )
		
		echo "Do you want to use this card (1/0)? Card : ${deck[26]}"
		
		read ch
		if [ $ch -eq 1 ]
		then
			echo "Which card you want to replace?"
			read var
			temp=${user[$var+1]}
			${user[$var+1]}=${deck[26]}
			${deck[26]}=$temp

		sum=0
		for i in 0 1 2 3 4 5 6 7 8 9 10 11 12
			sum+=${user[$i]}
			if [ $sum -eq 91 ]
			then
				echo "You Win....."
				user_win=1	
			fi	
		fi
		     
	fi


	echo "Your Cards : "
	for i in 0 1 2 3 4 5 6 7 8 9 10 11 12 
		do
			if [ ${computer[$i]} -eq 1 ]
			then
				echo "A"
			elif [ ${computer[$i]} -eq 11 ]
			then
				echo "J"
			elif [ ${computer[$i]} -eq 12 ]
			then
				echo "Q"
			elif [ ${computer[$i]} -eq 13 ]
			then
				echo "K"
			else
				echo ${computer[$i]}
			fi
		done
done
