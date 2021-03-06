Attending: Will, Petr, Jason, Jean-Marie, Mark, June, Wilma, Simon,
Andreas, Kevin, Melissa, Josh, David, Erin, Emil, Seb (14:17)

Start: 2:00 pm

1. Accepting minutes from [<u>last meeting</u>](https://drive.google.com/open?id=0B9Xg53EhqUycZEVHclBwRHNFRGM)
--------------------------------------------------------------------------------------------------------------

2. Project Status
-----------------

(2-3 minutes each)

-   IDR

    -   New data upload mechanism:

    -   IDR 0.8.5 released: two new 3D mouse studies

    -   IDR 0.8.6: WSI data: a new histopathology study with lung cancer
        > images + 1000 new HPA antibodies

-   NGFF

    -   S3 fun (CORS, public, private, clients, etc.)

        -   Some testing this morning - OK. Fast(ish) but not as fast as
            > Aspera

    -   Visualization clients

    -   EBI feedback. JavaScript apps using EBI s3 failed because of
        > CORS.

        -   Current workaround needs local copy etc.

    -   Simon: using Amazon JS viewer to browse idr-upload

    -   Need a web upload client via minio

    -   Simon: re-use OMERO.dropbox? Josh: yes, possible using minio
        > events

    -   [<u>Masks in
        > omero-ms-zarr</u>](https://github.com/ome/omero-ms-zarr/pull/60):
        > overlapping

        -   Updating other repos: ome-zarr-py, omero-cli-zarr

    -   Pushing on the final breaking changes (“labels/”)

        -   Python easy update, Java harder

    -   Next steps: handle multi-resolution zarr.

        -   JM - already had issues with this being missing

    -   Use cases, drivers, etc.

    -   JM: Cellprofiler (python2) issues with zarr - need to test again

    -   Jason: will provide datasets to test, with masks.

    -   Viv (Trevor) aims to add labels support

-   OMERO 5:

    -   deep copy (Mark)

        -   burrowing into repository and DAO code

    -   chown (Will/Petr)

        -   Will: chown is quite conservative, not wanting to end up in
            > a situation where hierarchies belong to different users
            > (at least in R-O and R-A). The webclient, however, allows
            > you to create such hierarchies by dragging things from one
            > container to another. The discrepancy leads to links being
            > cut.

            -   Change the server? Change chown? Handle it in the
                > client?

        -   Petr: “chown … will cut the link on me” isn’t how I
            > understood it. Instead:

            -   From a low-level, when you talk to OMERO permissions
                > people are shutting off. They don’t want to hear “link
                > is cut”. → “Why?!” (They don’t care about R-O or R-A)
                > The more complex the rules the deeper the hole we are
                > digging for ourselves. Intuitive expectation:
                > “everything will stay the same except what I want to
                > move.“

        -   Jason: links shouldn’t be cut?

        -   Petr: exactly! NO links should ever be cut.

            -   Deep copy work very high priority to fix this issue
                > between groups.

        -   Mark: received wisdom was P/D/I groups were ‘same owner’

        -   Josh: chown should fail. And give user options for how to
            > fix it: unlink, deep-copy

        -   Mark: ability to query which links will be broken during
            > change ownership, before running the chown command

    -   anything else? (component releases?)

-   SA: Josh: pgslave is growing

-   Glencoe: Emil

    -   n5/zarr looking at open-cv for downsampling

    -   Tile-db instead of pytables?

    -   Omero microservices for 3D analysis, imput from s3 buckets

    -   Josh: what do you want to try

    -   Emil: labelled masks, WSI. Can convert slides and create masks

    -   

-   Community

    -   CLA and Code of Conduct in Draft

    -   Sanger proposal funded - single cell imaging/analysis

    -   

3. AOB
------

(5 min. max; tech. Discussion should be highlighted to relevant people
and rescheduled)

4. Main Topic
-------------

(20-25 minutes plus 15 minutes questions max)
