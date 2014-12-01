YaleBikeShare
=============
Group Members:
Daniel Bond 
Laura Tucker
Skylar Shibayama
William Eckner
=============


public class TestEmail {
  public static void main (String[] args){
		
		String email = new String("firstName.lastName@Yale.edu");
		//email is not case sensitive
		//checks that the email is a Yale email 
		//with a first and last name separated by "."
		//the names can only contain letters
		if(checkEmail(email)){
			System.out.println("email is valid");
		}
		else{
			System.out.println("Please enter a valid Yale email address");
		}
		String password = new String("1Ab@1Ab@");
		//is greater than 8 characters
		//has at least one uppercase letter
		//has at least one lowercase letter
		//has at least one number
		//has at least one character
		if(checkPassword(password)){
			System.out.print("yeah");
		}
		else{
			System.out.println("nope");
		}
	}
	//methods (there are six):
	public static boolean checkEmail(String email){
		int l = email.length();
		if(l>74){
			return false;
		}
		if(true != endIsValid(email)){
			return false;
		}
		if (email.indexOf(".")>email.indexOf("@")||email.indexOf(".")==-1){
			return false;
		}
		if(true !=namesAreValid(email)){
			return false;
		}
		
		
		return true;
	}
    public static boolean isLetter(char ww){
    	char[] ll = {'a','b','c','d','e','f','g','h','i','j','k','l','m',
    			'o','n','p','q','r','s','t','u','v','w','x','y','z',
    			'A','B','C','D','E','F','G','H','I','J','K','L','M',
    			'O','N','P','Q','R','S','T','U','V','W','X','Y','Z'};
    	int i = 0;
    	while(i<52){
    		if(ww==ll[i]){
    			return true;
    		}
    		i++;
    	}
    	return false;
    }
    
    public static boolean isNumber(char w){
    	if(w=='0'||w=='1'||w=='2'||w=='3'||w=='4'||
				w=='5'||w=='6'||w=='7'||w=='8'||w=='9'){
    		return true;
    	}
    	else{
    		return false;
    	}
    }
    
    public static boolean endIsValid(String email){
    	//checks that the email ends with "@yale.edu"
		String properEnd = new String("@yale.edu");
		String end = email.substring(email.indexOf('@'), email.length());
		if (end.toLowerCase().equals(properEnd) != true){
			return false;
		}
    	return true;
    }
    
    public static boolean namesAreValid(String email){
    	//checks that the names contain only letters (uppercase or lowercase)
    	String firstName= email.substring(0,email.indexOf("."));
		String secondName= email.substring(email.indexOf(".")+1,email.indexOf("@"));
		for(int i =0; i< firstName.length(); i++){
			if(isLetter(firstName.charAt(i)) != true){
				return false;
			}
		}
		for(int i =0; i< secondName.length(); i++){
			if(true != isLetter(secondName.charAt(i))){
				return false;
			}
		}
    	
    	return true;
    }
    
    public static boolean checkPassword(String password){
    	String pass = null;
    	
    	//check that length is greater than or equal to 8
    	if(password.length()<8){
    		return false;
    	}
    	
    	//check that there is an uppercase letter
    	if(password.toLowerCase().equals(password)){
    		return false;
    	}
    	
    	//check that there is an uppercase letter
    	if(password.toUpperCase().equals(password)){
    		return false;
    	}
    	
    	//check that there is a number
    	pass = password;
    	for(int i=0; i<password.length(); i++){
    		if(isNumber(password.charAt(i))){
    			pass = pass.replace(password.charAt(i), 'w');
    		}
    	}
    	if(pass.equals(password)){
    		return false;
    	}
    	
    	//check that there is a character that isn't a letter or number
      String pass2 = pass;
    	for(int i=0; i<password.length(); i++){
    		if(isLetter(pass.charAt(i))){
    			pass2 = pass2.replace(pass.charAt(i), '1');
    		}
    	}
    	String ones = new String("");
    	for(int i=0; i <pass2.length(); i++){
    		ones += "1";
    	}
    	if (ones.equals(pass2)){
    		return false;
    	}
    	
    	return true;
    }

}
