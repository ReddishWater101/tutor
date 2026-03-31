This is problem 3.

The current policy is

`q = 1200`

`r = 640`

The lead time is `4 weeks`.

Weekly demand has

`mu_D = 150`

`sigma_D = 18`

So the demand-during-lead-time parameters are

`mu_L = 4 * 150 = 600`

`sigma_L = sqrt(4) * 18 = 36`

Now compute the z-value:

`z = (r - mu_L) / sigma_L`

`z = (640 - 600) / 36`

`z = 40 / 36`

`z = 1.1111`

Part a asks for the expected Type I service level.

Type I service level is

`alpha = F(r) = Phi(z)`

So

`alpha = Phi(1.1111)`

`alpha = 0.8667`

So the answer to part a is

`Type I service level = 0.8667`

Part b asks for the expected Type II service level.

First compute `n(r)` using the loss function:

`n(r) = sigma_L L(z)`

With `z = 1.1111`, the loss-function value is

`L(z) = 0.067125`

So

`n(r) = 36 * 0.067125`

`n(r) = 2.4165`

Now compute Type II service level:

`beta = 1 - n(r)/q`

`beta = 1 - 2.4165/1200`

`beta = 0.997986`

So the answer to part b is

`Type II service level = 0.9980`

Final answers:

`Part a: 0.8667`

`Part b: 0.9980`
