# Powershell-ISE-and-scripting

<img width="182" alt="Screenshot 2024-06-15 at 6 25 02 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/9a1926b7-a6fa-499b-86c8-0edacce90832">

<h1>Summary</h1>
In this lab we will use Powershell ISE (Integrated Scripting Environment). We will use Powershell ISE to create a text file, add information to that file, and then finally we will extract information from that file and use that data to create AD Users

<h1>Step 1) Creating a Text File</h1>

First let's create a text file 

To do that we can use New-Item we'll call it names.txt

<img width="904" alt="Screenshot 2024-06-02 at 2 05 28 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/739c1e6b-5869-4e4b-8902-48019a0e6cae">

With that we have created a text file in the users folder

<h1>Writing Data to our Text File</h1>

Now lets add some names to the text field

<img width="898" alt="Screenshot 2024-06-02 at 2 14 51 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/0b7ea258-f79a-44ac-a229-9a5e1b4e3f7c">

To do this we can provide a string and use the pipeline to send that string to Out-File

Out-File takes that string and puts it into the file we specify

<img width="903" alt="Screenshot 2024-06-02 at 2 22 23 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/e94d81ec-833b-4d38-a880-43b5e642ea30">

Now after we have our first name we need to use the append parameteter

This stops Powershell from just overwriting our string and adds on from the previous string

<img width="904" alt="Screenshot 2024-06-02 at 2 26 13 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/218fbd0b-c0a8-415e-8d07-9c75b36ac6d6">

We can check our names.txt file and see that all of our names have been created

<img width="801" alt="Screenshot 2024-06-02 at 2 26 58 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/e3efd545-162e-48f2-8936-1555c5573c45">

<h1>Step 3) Scripting with Powershell ISE</h1>

Now we can do a little bit of scripting 

Let's log our names to our Powershell console

<img width="900" alt="Screenshot 2024-06-02 at 2 36 52 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/bcea59e4-9354-4387-8858-10870d4826ce">

At the top part of the screen we can see $names = Get-Content names.txt

With that line of code we are creating a variable called $names

We declare a variable using the $ sign

We then set our $names variable to the value of our names.txt file using get-content

Then on line 3 we write the value of $names to the command line

Now let's loop through each name and add a little to each name

<img width="903" alt="Screenshot 2024-06-02 at 2 53 42 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/46f26818-04b6-45fb-934c-29cbcb4de5a9">

Once again we have declared our variable in line 1 of our code

Then you can see we have used the pipeline to put the value of our variable into a forEach-Object

A forEach-Object will loop through the objects we have provided via the pipeline

All we have done in this loop is write Hello my name is followed by each value of our text file

Since our string includes spaces we have used parenthesis

Since our variable is within parenthesis we need to do a little extra to declare our variable

We do this by encapsulating our variable within $()

Since we have already provided our variable with the pipeline we need to provide the property

An Object is a data structure with a bunch of properties

Since we do not have any properties for our object we can just use $_ which is inside the $()

Now instead of just printing the names let's create a simple active directory user

<img width="898" alt="Screenshot 2024-06-02 at 3 35 51 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/413c555e-6aca-4734-99eb-f6729202f066">

With this script we are creating a new user in our users OU which is inside of our IT OU which is within our ITlab.org domain


<img width="748" alt="Screenshot 2024-06-02 at 3 35 29 PM" src="https://github.com/Jtalbert15/Powershell-ISE-and-scripting/assets/66844406/068d49a6-6b82-46c7-9b94-1969940bb19e">

We can see that we have successfully created our users within our users OU
