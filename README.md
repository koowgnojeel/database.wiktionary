## Wiktionary data for MariaDB


### Count of data

322,945


### Data Definition Language(DDL)

```SQL
CREATE TABLE `wiktionary` (
     `fm_id`                  int(10)       unsigned              NOT NULL   AUTO_INCREMENT
    ,`log_fm_id`              int(10)       unsigned DEFAULT NULL
    ,`lang_dtct_inq_data`     varchar(70)                         NOT NULL
    ,`lang_dtct_req_url`      varchar(500)                        NOT NULL
    ,`lang_dtct_err_cd`       varchar(20)                         NOT NULL
    ,`lang_dtct_err_msg`      varchar(1000)                       NOT NULL
    ,`lang_dtct_redirect_url` varchar(500)                        NOT NULL
    ,`lang_dtct_resp`         mediumtext                          NOT NULL
    ,`lang_dtct_start_utc_dt` varchar(31)                         NOT NULL
    ,`lang_dtct_end_utc_dt`   varchar(31)                         NOT NULL
    ,`suggest_inq_data`       varchar(70)                         NOT NULL
    ,`suggest_resp`           mediumtext                          NOT NULL
    ,`suggest_start_utc_dt`   varchar(31)                         NOT NULL
    ,`suggest_end_utc_dt`     varchar(31)                         NOT NULL
    ,`wik_inq_first_char`     varchar(1)                          NOT NULL
    ,`wik_inq_data`           varchar(70)                         NOT NULL
    ,`wik_resp`               mediumtext                          NOT NULL
    ,`naver1_resp`            mediumtext             DEFAULT NULL
    ,`naver2_resp`            mediumtext             DEFAULT NULL
    ,`wik_start_utc_dt`       varchar(31)                         NOT NULL
    ,`wik_end_utc_dt`         varchar(31)                         NOT NULL

    ,PRIMARY KEY (`fm_id`)
    ,UNIQUE  KEY `wik_inq_data` (`wik_inq_data`)
    ,KEY         `idx_wik_inq_first_char` (`wik_inq_first_char`)
) 
ENGINE=InnoDB
AUTO_INCREMENT=351443
DEFAULT
CHARSET=utf8mb4
COLLATE=utf8mb4_bin
;
```


### Physical/logical column mappings

| Physical column name    | Description                                         | 
|-------------------------|-----------------------------------------------------| 
| `fm_id`                 | Record ID                                           | 
| `log_fm_id`             | Temp field(for migration)                           |
|                         |                                                     | 
| `lang_dtct_inq_data`    | Inquiry word for language detection                 | 
| `lang_dtct_req_url`     | Language detection URL                              | 
| `lang_dtct_err_cd`      | Response code of language detection URL             | 
| `lang_dtct_err_msg`     | Response message of language detection URL          | 
| `lang_dtct_redirect_url`| Redirection URL of language detection URL           | 
| `lang_dtct_resp`        | Language of this word                               | 
| `lang_dtct_start_utc_dt`| Language detection beginning timestamp in UTC       | 
| `lang_dtct_end_utc_dt`  | Language detection end timestamp in UTC             | 
|                         |                                                     | 
| `suggest_inq_data`      | Inquiry word for word suggestion                    | 
| `suggest_resp`          | Suggestions                                         | 
| `suggest_start_utc_dt`  | Suggestion inquiry beginning timestamp in UTC       | 
| `suggest_end_utc_dt`    | Suggestion inquiry end timestamp in UTC             | 
|                         |                                                     | 
| `wik_inq_first_char`    | The first letter of the Wiktionary word inquiry     | 
| `wik_inq_data`          | Inquiry word for Wiktionary                         | 
| `wik_resp`              | Wiktionary result                                   | 
| `naver1_resp`           | Naver Korean dictionary inquiry result(1)           | 
| `naver2_resp`           | Naver Korean dictionary inquiry result(2)           | 
| `wik_start_utc_dt`      | The whole process beginning timestamp in UTC        | 
| `wik_end_utc_dt`        | The whole process end timestamp in UTC              | 


### Sample data

```plain
fm_id                  : 351441
log_fm_id              : 
lang_dtct_inq_data     : novels
lang_dtct_req_url      : http://en.wiktionary.org/wiki/novels
lang_dtct_err_cd       : 0
lang_dtct_err_msg      : 
lang_dtct_redirect_url : 
lang_dtct_resp         : English
lang_dtct_start_utc_dt : 2023-02-26T14:34:40,777330+0000
lang_dtct_end_utc_dt   : 2023-02-26T14:34:42,206456+0000
suggest_inq_data       : novels
suggest_resp           : novels,novel,novela,novella,novelle,novell,novelty,novelty theory,novello,novelli
suggest_start_utc_dt   : 2023-02-26T14:34:39,658612+0000
suggest_end_utc_dt     : 2023-02-26T14:34:40,777282+0000
wik_inq_first_char     : n
wik_inq_data           : novels
wik_resp               : [
      {
        "etymology": "",
        "definitions": [
          {
            "partOfSpeech": "noun",
            "text": [
              "novels",
              "plural of novel"
            ],
            "relatedWords": [],
            "examples": []
          }
        ],
        "pronunciations": {
          "text": [
            "(General American) enPR: nävʹəlz, IPA: /ˈnɑvl̩z/",
            "(Received Pronunciation) enPR: nŏvʹəlz, IPA: /ˈnɒvl̩z/",
            "Hyphenation: nov‧els"
          ],
          "audio": []
        }
      }
    ]
naver1_resp            : 
    [News & Media] (Abbr.) N.novel[ˈnɑːvl, ˈnɒvl]  1. [명사] (장편) 소설  2.
    [형용사][흔히 호감] (이전에 볼 수 없던) 새로운, 신기한 신기한, 새로운, 기발한,
    참신한; 소설novelty[│nɑːvlti, │nɒvlti]  1. [명사] 새로움, 참신함, 신기함  2.
    [명사] 새로운[참신한/신기한] 사람[것]  3. [형용사] 색다른, 진기한 소설
naver2_resp            : 
    Novels
    [News & Media] (Abbr.) N.
    novel (novels) 미국식 [ˈnɑːvl] 영국식 [ˈnɒvl]
    1. [명사] (장편) 소설 
    2. [형용사][흔히 호감] (이전에 볼 수 없던) 새로운, 신기한
    novel (novels) 신기한, 새로운, 기발한, 참신한; 소설
    novelty (novels) 미국식 [│nɑːvlti] 영국식 [│nɒvlti]
    1. [명사] 새로움, 참신함, 신기함 
    2. [명사] 새로운[참신한/신기한] 사람[것] 
    3. [형용사] 색다른, 진기한
    Novel (novels) 소설
wik_start_utc_dt       : 2023-02-26T14:34:42,206529+0000
wik_end_utc_dt         : 2023-02-26T14:34:42,936020+0000
```


### Load script

* To extract tar archive, use

```Bash
$ cat wiktionary.sql.tgz.* | tar -xzvf -
```

* And simply copy/paste DDL script above into SQL client to create a target table.
* Then execute blow script to load data into MariaDB.

```Bash
$ mysql -u USER -pPASSWORD DATABASE < wiktionary.sql;
```

