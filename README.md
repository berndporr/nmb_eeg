# Pure EEG power

Log Power spectra of pure EEG from two temporarily paralysed
subjects. Data adapted from the figures in:

[Scalp electrical recording during paralysis: Quantitative evidence that
EEG frequencies above 20 Hz are contaminated by EMG
Emma M. Whitham a , Kenneth J. Pope b , Sean P. Fitzgibbon c , Trent Lewis b ,
C. Richard Clark c , Stephen Loveless d , Marita Broberg e , Angus Wallace e ,
Dylan DeLosAngeles e , Peter Lillie f , Andrew Hardy f , Rik](https://www.sciencedirect.com/science/article/abs/pii/S1388245707001988)

by having manually clicked on the datapoints of the 6 PSD plots
in the paper and then done a polynomial fit to smooth out the errors
from the manual reconstruction.

![alt tag](individual_average.png)

## Usage

To obtain the average PSD over all experiments just use
the default constructor:
```
p = ParalysedEEGFromWhithamEtAl()
```

If you want to extract the PSD based on one dataset do
```
p = ParalysedEEGFromWhithamEtAl(1)
```
which selects dataset 1.

Obtain the power spectral density by providing either
a single frequency f or an array to calculate multiple
points:
```
psd = p.EEGVariance(f)
```

Or the total power of the entire frequency range:
```
totalEEGPower = p.totalEEGPower()
```

The frequency range can be obtained from `f_signal_min` and
`p.f_signal_max` which can be used to generate the frequency
axis:

```
f = np.linspace(p.f_signal_min,p.f_signal_max,100)
```

Because `EEGVariance(f)` accepts an array plotting the spectrum
can simply be done with:

```
plt.plot(f,p.EEGVariance(f))
```

### Usage example code

Run:
```
plot_paralysed_EEG_PSD.py
```
which generates the plot at the top of this page.

# Credit

Bernd Porr <bernd.porr@glasgow.ac.uk>
