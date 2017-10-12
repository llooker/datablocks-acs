# DDL Statements

Use the following DDL statements as a reference and starting point for uploading our datasets into your own DB.

Note: *Our DDL statments follow Amazon Redshift Spectrum syntax. You may need to adjust data types and other fields as necessary for your dialect.*
For Redshift you may want to reference the create/copy syntax from here: http://docs.aws.amazon.com/redshift/latest/dg/r_COPY.html


```
CREATE external TABLE zcta_distances(
   zip1        INTEGER  PRIMARY KEY
  ,zip2        INTEGER
  ,mi_to_zcta5 NUMERIC(16,13)
)
row format delimited
fields terminated by ','
stored as textfile
location 's3://looker-datablocks/acs_fast_facts/zcta_distances/';
```

```
CREATE external TABLE zcta_to_tract_w_state(
   ZCTA5              INTEGER
  ,STATE              VARCHAR(2)
  ,COUNTY             VARCHAR(3)
  ,TRACT              INTEGER
  ,GEOID              INTEGER
  ,POPPT              INTEGER
  ,HUPT               INTEGER
  ,AREAPT             INTEGER
  ,_AREALANDPT        INTEGER
  ,ZPOP               INTEGER
  ,ZHU                INTEGER
  ,ZAREA              INTEGER
  ,ZAREALAND          INTEGER
  ,TRPOP              INTEGER
  ,TRHU               INTEGER
  ,TRAREA             INTEGER
  ,TRAREALAND         INTEGER
  ,ZPOPPCT            NUMERIC(5,2)
  ,ZHUPCT             NUMERIC(5,2)
  ,ZAREAPCT           NUMERIC(5,2)
  ,ZAREALANDPCT       NUMERIC(5,2)
  ,TRPOPPCT           NUMERIC(5,2)
  ,TRHUPCT            NUMERIC(5,2)
  ,TRAREAPCT          NUMERIC(5,2)
  ,TRAREALANDPCT      NUMERIC(5,2)
  ,state_name         VARCHAR(15)
  ,fips               INTEGER
  ,state_abbreviation VARCHAR(2)
)
row format delimited
fields terminated by ','
stored as textfile
location 's3://looker-datablocks/acs_fast_facts/zcta_to_tract_w_state/';
```


```
CREATE external TABLE fast_facts(
   logrecno_bg_map_block_group VARCHAR(12) PRIMARY KEY
  ,total_population            INTEGER
  ,housing_units               INTEGER
  ,female                      INTEGER
  ,male                        INTEGER
  ,white_alone_or_in_combo     INTEGER
  ,black_alone_or_in_combo     INTEGER
  ,amind_alone_or_in_combo     INTEGER
  ,asian_alone_or_in_combo     INTEGER
  ,nat_haw_alone_or_in_combo   INTEGER
  ,hispanic_or_latino          INTEGER
  ,white_non_hisp              INTEGER
  ,under_18                    INTEGER
  ,eighteen_to_64              INTEGER
  ,sixty_five_and_over         INTEGER
  ,aggregate_income            INTEGER
)
row format delimited
fields terminated by ','
stored as textfile
location 's3://looker-datablocks/acs_fast_facts/fast_facts/';
```

```
CREATE external TABLE geo2015(
   FILEID    VARCHAR2(5) PRIMARY KEY
  ,STUSAB    VARCHAR2(2)
  ,SUMLEVEL  INTEGER
  ,COMPONENT INTEGER
  ,LOGRECNO  INTEGER
  ,US        VARCHAR2(30)
  ,REGION    VARCHAR2(30)
  ,DIVISION  VARCHAR2(30)
  ,STATECE   VARCHAR2(30)
  ,STATE     VARCHAR(30)
  ,COUNTY    VARCHAR(30)
  ,COUSUB    VARCHAR(30)
  ,PLACE     VARCHAR(30)
  ,TRACT     VARCHAR(30)
  ,BLKGRP    VARCHAR(30)
  ,CONCIT    VARCHAR(30)
  ,AIANHH    VARCHAR(30)
  ,AIANHHFP  VARCHAR(30)
  ,AIHHTLI   VARCHAR(30)
  ,AITSCE    VARCHAR(30)
  ,AITS      VARCHAR(30)
  ,ANRC      VARCHAR(30)
  ,CBSA      INTEGER
  ,CSA       INTEGER
  ,METDIV    VARCHAR(30)
  ,MACC      VARCHAR(30)
  ,MEMI      VARCHAR(30)
  ,NECTA     VARCHAR(30)
  ,CNECTA    VARCHAR(30)
  ,NECTADIV  VARCHAR(30)
  ,UA        INTEGER
  ,BLANK1    VARCHAR(30)
  ,CDCURR    VARCHAR(30)
  ,SLDU      VARCHAR(30)
  ,SLDL      VARCHAR(30)
  ,BLANK2    VARCHAR(30)
  ,BLANK3    VARCHAR(30)
  ,ZCTA5     INTEGER
  ,SUBMCD    VARCHAR(30)
  ,SDELM     VARCHAR(30)
  ,SDSEC     VARCHAR(30)
  ,SDUNI     VARCHAR(30)
  ,UR        VARCHAR(30)
  ,PCI       VARCHAR(30)
  ,BLANK4    VARCHAR(30)
  ,BLANK5    VARCHAR(30)
  ,PUMA5     VARCHAR(30)
  ,BLANK6    VARCHAR(30)
  ,GEOID     VARCHAR(15)
  ,NAME      VARCHAR(54)
  ,BTTR      VARCHAR(30)
  ,BTBG      VARCHAR(30)
  ,BLANK7    VARCHAR(30)
)
row format delimited
fields terminated by ','
stored as textfile
location 's3://looker-datablocks/acs_fast_facts/geo_2015/';
```
