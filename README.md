# utl-sas-version-of-R-histogram-with-error-bars-and-xaxis-table
sas version of R histogram with error bars and xaxis table 
    %let pgm=utl-sas-version-of-R-histogram-with-error-bars-and-xaxis-table;

    sas version of R histogram with error bars and xaxis table

    I think the SAS rendering is superior to the R rendering?

    github
    https://tinyurl.com/4crvv3pb
    https://github.com/rogerjdeangelis/utl-sas-version-of-R-histogram-with-error-bars-and-xaxis-table

    github graph
    https://tinyurl.com/5mvz9us5
    https://github.com/rogerjdeangelis/utl-sas-version-of-R-histogram-with-error-bars-and-xaxis-table/blob/main/utl-sas-version-of-R-histogram-with-error-bars-and-xaxis-table

    github
    https://tinyurl.com/ymufdej4
    https://stackoverflow.com/questions/75999054/trying-to-create-prevalence-chart-with-error-bars-and-percentages

    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */
    libname sd1 "d:/sd1";

    data sd1.have;
       informat disability $16.;
       input disability prevalence lower upper;
    cards4;
    Physical 86.38 84.75 88.01
    Cognitive 83.42 81.95 84.85
    Both 80.71 78.23 83.19
    No 88.26 87.76 88.76
    Age 86.38 84.75 88.01
    Score 83.42 81.95 84.85
    Hours 80.71 78.23 83.19
    Minutes 88.26 87.76 88.76
    Days 86.38 84.75 88.01
    Weeks 83.42 81.95 84.85
    Meetings 80.71 78.23 83.19
    Luncheons 88.26 87.76 88.76
    ;;;;
    run;quit;

    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /* Up to 40 obs from SD1.HAVE total obs=12 19APR2023:16:26:35                                                             */
    /*                                                                                                                        */
    /*                                histogram error bars                                                                    */
    /*                                   ================                                                                     */
    /* Obs    DISABILITY    PREVALENCE    LOWER    UPPER                                                                      */
    /*                                                                                                                        */
    /*   1    Physical         86.38      84.75    88.01                                                                      */
    /*   2    Cognitive        83.42      81.95    84.85                                                                      */
    /*   3    Both             80.71      78.23    83.19                                                                      */
    /*   4    No               88.26      87.76    88.76                                                                      */
    /*   5    Age              86.38      84.75    88.01                                                                      */
    /*   6    Score            83.42      81.95    84.85                                                                      */
    /*   7    Hours            80.71      78.23    83.19                                                                      */
    /*   8    Minutes          88.26      87.76    88.76                                                                      */
    /*   9    Days             86.38      84.75    88.01                                                                      */
    /*  10    Weeks            83.42      81.95    84.85                                                                      */
    /*  11    Meetings         80.71      78.23    83.19                                                                      */
    /*  12    Luncheons        88.26      87.76    88.76                                                                      */
    /*                                                                                                                        */
    /**************************************************************************************************************************/

    /*           _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| `_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    */

    github graph
    https://tinyurl.com/5mvz9us5

    d:\pdf\utl-sas-version-of-R-histogram-with-error-bars-and-xaxis-table.pdf

    /*
     ___  __ _ ___   _ __  _ __ ___   ___ ___  ___ ___
    / __|/ _` / __| | `_ \| `__/ _ \ / __/ _ \/ __/ __|
    \__ \ (_| \__ \ | |_) | | | (_) | (_|  __/\__ \__ \
    |___/\__,_|___/ | .__/|_|  \___/ \___\___||___/___/
                    |_|
    */

    %utlfkil(d:/pdf/sas_hist.pdf);
    ods pdf file="d:/pdf/utl-sas-version-of-R-histogram-with-error-bars-and-xaxis-table.pdf" style=pearl;
    title 'Histogram with error bars and xxais table beeter than the R graph';
    proc sgplot data=sd1.have noautolegend;
       vbarparm
          category       = disability
          response       = prevalence
           /group        = disability
            groupdisplay = cluster
            fillattrs    = (color="light gray") ;
    highlow x    = disability
            low  = lower
            high = upper
            / highcap = serif
              lowcap  = serif
              lineattrs = (color=black) ;
    yaxis min           =75 ;
    xaxis valueattrs= (size=11pt) display=(noticks) labelattrs=(size=11pt);;
    xaxistable upper prevalence lower
           /location         = inside
            valueattrs       = (color=blue size=9pt)
            labelattrs=(size=9pt);
    run;quit;
    ods pdf close;

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */





