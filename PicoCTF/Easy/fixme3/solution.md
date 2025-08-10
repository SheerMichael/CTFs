# Solution


```
    // unsafe {
        // Decrypt the flag operations 
        let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);

        // Creating a pointer 
        let decrypted_ptr = decrypted_buffer.as_ptr();
        let decrypted_len = decrypted_buffer.len();
        
        // Unsafe operation: calling an unsafe function that dereferences a raw pointer
        let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);

        borrowed_string.push_str(&String::from_utf8_lossy(decrypted_slice));
    // }
    println!("{}", borrowed_string);
}
```

notice how parts of the code are commented out:
<mark> // unsafe {} </mark>
    and the closing tag in the same block
    <mark> // } </mark>

We simply remove the comment symbol and run the code.
We get the flag: <mark>_picoCTF{n0w_y0uv3_f1x3d_1h3m_411}_</mark> 