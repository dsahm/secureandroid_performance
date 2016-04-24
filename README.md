# secureandroid_performance

This is a fork of SecureAndroid suited better for performance-critical operations. The only difference to SecureAndroid is that the password is not checked for correctness.
This saves the PBKDF-Iterations for this task and thus improves performance significantly. It is important to note that this change
does NOT decrease the security of the encryption in any way. It only decreases the comfort in handling SecureAndroid because now
it is not possible to say that an encryption or decryption failed because of a wrong password. The enc- or decryption still fails only
that now most likely the IntegrityCheckFailedExceptin or the BadPaddingException will be thrown. This means you might no be able
to tell the user exactly WHY the encryption or decryption failed. But it still will fail. Using SecureAndroid in this way does therefore
not decrease security but only decreases the comfort in Exception-Handling. 

