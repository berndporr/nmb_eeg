Pure EEG power during paralysis
===============================

Power spectra of pure EEG from two temporarily paralysed subjects.

Data from (Fig 1, B-traces):

`Scalp electrical recording during paralysis: Quantitative evidence that
EEG frequencies above 20 Hz are contaminated by EMG
Emma M. Whitham, Kenneth J. Pope, Sean P. Fitzgibbon, Trent Lewis,
C. Richard Clark, Stephen Loveless, Marita Broberg, Angus Wallace,
Dylan DeLosAngeles, Peter Lillie, Andrew Hardy, Rik.
Clinical Neurophysiology Volume 118, Issue 8, August 2007,
Pages 1877-1888. <https://www.sciencedirect.com/science/article/abs/pii/S1388245707001988>`_

Please cite as "Data from ..." as outlined above. This has been advised by Elsevier's Copyrights Coordinator.


Usage
-----

To obtain the average PSD over all experiments just use
the default constructor::

  p = NMB_EEG_From_WhithamEtAl()


If you want to extract the PSD of dataset one do::

  p = NMB_EEG_From_WhithamEtAl(1)


Obtain the power spectral density in V^2/Hz use::

  psd = p.EEGVariance(f)

where `f` can be either a single frequency or a numpy array.
The lowest permitted frequency is
`f_signal_min` and the highest `f_signal_max`.

The total power of the entire frequency range from `f_signal_min` to `f_signal_max` is::

  totalEEGPower = p.totalEEGPower()


Because `EEGVariance(f)` accepts a numpy array plotting the spectrum is simply::

  f = np.linspace(p.f_signal_min,p.f_signal_max,100)
  plt.plot(f,p.EEGVariance(f))



Usage example
-------------

Run::

  plot_paralysed_EEG_PSD.py

from the github page: https://github.com/berndporr/nmb_eeg


Credit
------

Bernd Porr <bernd.porr@glasgow.ac.uk>



.. image:: https://zenodo.org/badge/529194569.svg
   :target: https://zenodo.org/badge/latestdoi/529194569
