# Seam-Carving-Project
## Video URL
<https://youtu.be/aEH4dZyuOts>

## Brief description
    This is Seam Carving Project from course Comp572. The main idea of seam carving is to resize the image but preserve the most interesting/significant 
    features (subject ratio, etc.). Since scaling would distort the image, and cropping would remove certain features.
[![IMAGE ALT TEXT HERE](https://user-images.githubusercontent.com/59798959/185551359-826d9238-09cb-4538-bae2-5f6d1668246c.png)

## Takeaways:
    For the energy function I used the gradient magnitude approach mentioned in
    HW4. The idea is that only pixels with gradient magnitude would get
    selected for edge image. So I first use a Gaussian blur filter with sigma=1
    to help neglect insignificant details and then applied Sobel filter on the
    blurred image to compute individual gradients on both x and y direction.
    Then, the total gradient magnitude can be calculated by using pythagoras theorem.
    
    What is specifically challenging is to correctly record the minimum amount
    energy needed to get to a specific pixel(Energy Map) and identifying the direction of
    backtrace accordingly. I started with bottom-to-up approach for vertical
    carving, yet the effect is not ideal compared with the top-to-bottom
    dynamic approach because important features in the image get removed much.
    This failure is probably because of inncorrect direction for backtracing,
    so the seam identified for removal is not entirely correct.
    Note: I used (-1,0,1) to denote (left, center, right)/ (up, center, low) of
    the three neighboring pixels in energy map and seam finding calculation.

    In particular, I added a small function to illustrate each seam identified
    in red color. By including it in the carving function that gets looped each time,
    I was able to create a dynamic video illustrating the shrinking of image with the corresponding
    next seam to be removed. This also helped a lot in my debugging progress.
    I commented for the sake of submission. To view how dynamic shrinking is done, simply
    uncomment lines 230-231, and 250-251.

## Output:
![Pic1](https://user-images.githubusercontent.com/59798959/185553897-6c4a2a0f-279b-4ae1-adf1-482868817d14.jpg)
![2](https://user-images.githubusercontent.com/59798959/185553920-7af9eb18-b90d-4950-9662-7716463adc3b.jpg)
![3](https://user-images.githubusercontent.com/59798959/185553931-48fb4add-5da8-4757-9c54-3264211edaf6.jpg)
![4](https://user-images.githubusercontent.com/59798959/185553945-b94ed14c-8bf1-4d5c-a8e9-3b99e27f45a9.jpg)
![Picture5](https://user-images.githubusercontent.com/59798959/185553952-03f5c5e9-6a46-4ed9-846e-12c3362de397.jpg)




