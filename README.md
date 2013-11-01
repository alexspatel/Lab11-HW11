Lab11-HW11
==========

Lab 11 and Homework 11 for CSCI 261

/*
 * CSCI 261 : Cryptography Lab
 *
 * Co-Author: Alex Patel
 *
 * Co-Author: _INSERT_YOUR_NAME_HERE_
 *
 * This program implements a stream cipher or keystream encryption algorithm to
 * encrypt a plain text string using a key string to produce a cipher text string.
 * The plain text string and key string are both entered by the user.
 */

#include <iostream>
#include <iomanip>
#include <fstream>
#include <cstdlib>
#include <cstring>
#include <string>
#include <cmath>
#include <ctime>
using namespace std;

// Setting these to 'A' and 26 only allows encryption of upper-case letters.
// This is good for testing, but setting these to a space, ' ', and 95 will
// allow encryption/decryption of most plain text strings/files.
const char FIRST_LETTER = 'A';  // Use 'A' or ' '.
const int FIRST_LETTER_SIZE = 0; // First letter equals A or 0.
const int ALPHABET_SIZE = 26;   // Use 26 or 95.
const char FINAL_LETTER = 'Z'

const int TXT_MAX = 80;
const int KEY_MAX = 16;

// Function prototypes.
char encryptChar( char key, char ch );
char decryptChar( char key, char ch );

void encryptString( const char keystream[], const char plaintext[], char ciphertext[] );
void decryptString( const char keystream[], const char ciphertext[], char plaintext[] );

void encryptFile( const char keystream[], const char plaintextfile[], char ciphertextfile[] );
void decryptFile( const char keystream[], const char ciphertextfile[], char plaintextfile[] );

int main()
{
  /******** INSERT YOUR CODE BELOW HERE ********/
  char A ='C', B;
  cout << "Enter a key to be encrypted: " ;
  cin >> B;

  char encryptedCharacter = encryptChar( A, B );
  cout << endl << encryptedCharacter << endl;

  char decryptedCharacter = decryptChar( A, B );
  cout << endl << decryptedCharacter << endl;

  




  /******** INSERT YOUR CODE ABOVE HERE ********/
}

/*
 * This function encrypts a single character using the given key,
 * returning the encrypted character.
 *
 *        *************************************
 *        **** DO NOT MODIFY THIS FUNCTION ****
 *        *************************************
 *
 * Pre-condition: The input values, ch and key, are valid char variables.
 * Post-condition: The value returned is ch encrypted with key, modulus
 *                 the alphabet size; if the input value of ch is not in
 *                 the alphabet, it is returned unchanged.
 */
char encryptChar( char key, char ch )
{
  // Make sure the character is within the range of our encryption.
  if( ch >= FIRST_LETTER && ch <= FIRST_LETTER + ALPHABET_SIZE )
  {
    // Convert ch to a value in the range 0 <= ch < ALPHABET_SIZE.
    ch -= FIRST_LETTER;
    // Convert key to a value in the range 0 <= key < ALPHABET_SIZE.
    key -= FIRST_LETTER;
    // Encrypt ch, using modulus to wrap around the alphabet, if necessary.
    ch = ( ch + key ) % ALPHABET_SIZE;
    // Convert the now encrypted ch back to a character in the alphabet.
    ch += FIRST_LETTER;
  }

  // Return the encrypted character, or the original character if it was out of range.
  return ch;
}

/*
 * This function decrypts a single character using the given key,
 * returning the decrypted character.
 *
 *        *************************************
 *        **** DO NOT MODIFY THIS FUNCTION ****
 *        *************************************
 *
 * Pre-condition: The input values, ch and key, are valid char variables.
 * Post-condition: The value returned is ch decrypted with key, modulus
 *                 the alphabet size; if the input value of ch is not in
 *                 the alphabet, it is returned unchanged.
 */
char decryptChar( char key, char ch )
{
  // Make sure the character is within the range of our encryption.
  if( ch >= FIRST_LETTER && ch <= FIRST_LETTER + ALPHABET_SIZE )
  {
    // Convert ch to a value in the range 0 <= ch < ALPHABET_SIZE.
    ch -= FIRST_LETTER;
    // Convert key to a value in the range 0 <= key < ALPHABET_SIZE.
    key -= FIRST_LETTER;
    // Decrypt ch, using modulus to wrap around the alphabet, if necessary.
    ch = ( ch + ALPHABET_SIZE - key ) % ALPHABET_SIZE;
    // Convert the now encrypted ch back to a character in the alphabet.
    ch += FIRST_LETTER;
  }

  // Return the decrypted character, or the original character if it was out of range.
  return ch;
}

/*
 * This function encrypts a character string using the given key string,
 * putting the resulting encrypted string into the given cipher text string.
 *
 * Pre-condition: The input values, plaintext and keystream, are valid
 *                C-style character strings terminted with a null character;
 *                ciphertext is valid C-style character string with as
 *                much memory space as the input plaintext string.
 * Post-condition: The input values, plaintext and keystream, are unchanged;
 *                 ciphertext contains the encrpyted version of the plaintext.
 */
void encryptString( const char keystream[], const char plaintext[], char ciphertext[] )
{
  /******** INSERT YOUR CODE BELOW HERE ********/
   // Make sure the string is within the range of our encryption.
  for( int i = 0; i < strlen(keystream); i++ )
  {
	    if( strlen(keystream) >= FIRST_LETTER && strlen(keystream) <= FIRST_LETTER + ALPHABET_SIZE )
	{
		// Convert ch to a value in the range 0 <= ch < ALPHABET_SIZE.
		plaintext -= FIRST_LETTER;
		// Convert key to a value in the range 0 <= key < ALPHABET_SIZE.
		keystream -= FIRST_LETTER;
		// Decrypt ch, using modulus to wrap around the alphabet, if necessary.
		plaintext = ( plaintext + ALPHABET_SIZE - keystream ) % ALPHABET_SIZE;
		// Convert the now encrypted ch back to a character in the alphabet.
		plaintext += FIRST_LETTER;
	}
  }



  /******** INSERT YOUR CODE ABOVE HERE ********/
}

/*
 * This function decrypts a character string using the given key string,
 * putting the resulting decrypted string into the given plain text string.
 *
 * Pre-condition: The input values, ciphertext and keystream, are valid
 *                C-style character strings terminted with a null character;
 *                plaintext is valid C-style character string with as
 *                much memory space as the input ciphertext string.
 * Post-condition: The input values, ciphertext and keystream, are unchanged;
 *                 plaintext contains the decrpyted version of the ciphertext.
 */
void decryptString( const char keystream[], const char ciphertext[], char plaintext[] )
{
  /******** INSERT YOUR CODE BELOW HERE ********/



  /******** INSERT YOUR CODE ABOVE HERE ********/
}

void encryptFile( const char keystream[], const char plaintextfile[], char ciphertextfile[] )
{
  /******** INSERT YOUR CODE BELOW HERE ********/



  /******** INSERT YOUR CODE ABOVE HERE ********/
}

void decryptFile( const char keystream[], const char ciphertextfile[], char plaintextfile[] )
{
  /******** INSERT YOUR CODE BELOW HERE ********/



  /******** INSERT YOUR CODE ABOVE HERE ********/
}

