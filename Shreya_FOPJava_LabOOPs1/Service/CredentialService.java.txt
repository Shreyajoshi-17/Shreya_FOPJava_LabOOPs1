package com.email.service;

import java.util.Random;

public class CredentialService {
	
	private static final String COMPANY = "abc";
	private static final String DELIMITER = "";
	private static final String CAPITAL_CHARS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
	private static final String SMALL_CHARS = "abcdefghijklmnopqrstuvwxyz";
	private static final String NUMBERS = "1234567890";
	private static final String SPECIAL_CHARS = "!@#$%^&*()_-";
 
	
	public static String generateEmailAddress(String firstName,String lastName,String dept) {
		String email = firstName.toLowerCase()+DELIMITER+lastName.toLowerCase()+"@"+dept.toLowerCase()+"."+COMPANY+"."+"com";
		return email;
	}
	
	public static String generatePassword(int length) {
		String value = CAPITAL_CHARS + SMALL_CHARS + NUMBERS + SPECIAL_CHARS;
		Random random = new Random();
		
		char[] password = new char[length];
		
		for (int i = 0; i < length; i++) {
			password[i] = value.charAt(random.nextInt(value.length()));
		}
		return String.valueOf(password);
	}
	
	public static void showCredentials(String firstName, String email, String password) {
		System.out.println("Dear " + firstName + " your generated credentials are as follows:");
		System.out.println("Email    ---> " + email);
		System.out.println("Password ---> " + password);
	}
}
