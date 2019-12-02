VO tools:

Web interface:

herschel-vos.phys.sussex.ac.uk

TAP service:

https://herschel-vos.phys.sussex.ac.uk/__system__/tap/run/tap



SELECT
    db.ID,
    db.RA,
    db.DEC,
    db.field,
    db.photo_z,
    db.photo_zerr,
    db.MASS_BEST,
    db.MASS_INF,
    db.MASS_SUP,
    db.SFR_BEST,
    db.SFR_INF,
    db.SFR_SUP,
    db.AGE_BEST,
    db.AGE_INF,
    db.AGE_SUP
    
FROM desi_photoz.main AS db
WHERE 1=CONTAINS(POINT('ICRS', db.ra,db.dec),
CIRCLE('ICRS', 3.7765, 14.2396, 100.0/3600.))
