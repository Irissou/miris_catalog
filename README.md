# miris_catalog

Catalog to the paper Jermann et al.: MIDIS: high-redshift JWST/MIRI-selected galaxies in the Hubble Ultra Deep Field.

This catalog contains the photometry and errors measured in apertures of D=0.4" in the MIRI Deep Imaging Survey of the HUDF (MIDIS). The MIDIS image is avaiable at https://doi.org/10.5281/zenodo.15624625 and the description of the survey is described in Östlin et al. 2025. The NIRCam and HST images are taken from the Dawn JWST Archive (https://dawn-cph.github.io/dja/index.html).

To read the catalog tables:

from astropy.io import fits
from astropy.table import Table

hdul = fits.open('MIRIS_catalog.fits')
print(hdul.info())

Science catalog with the photometry and associated errors in 3 MIRI, 14 NIRCam, and 9 HST filters. The full procedure of the catalog is described in Section 3.3 of the paper.
SCIENCE = Table(hdul['SCIENCE'].data)

Catalogs with information related to the detection of the sources in MIDIS Deep.
DETECTION = Table(hdul['DETECTION'].data)
PHOTOMETRY = Table(hdul['PHOTOMETRY'].data)

Catalog related to the selection of MIRI-red sources in the paper (Section 3.5).
MONTECARLO = Table(hdul['MONTECARLO'].data)

NIRCam parent catalog used in the estimate of the purity and the completeness of the MIRI-detected sources in MIDIS (Section 3.4).
NC_detection = Table(hdul['NIRCAM'].data)


The catalog is avaiable at the following link on Zenodo: 10.5281/zenodo.20747053. 
