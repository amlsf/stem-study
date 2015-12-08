# Feature Engineering

The following tables list the various household-level and person-level fields that are available on IPUMS-USA. For each field, we have included the original IPUMS field name and field description, as well as our rationale for excluding fields.



**Household - Technical Variables**

| Field name | Field description                        | Included | Rationale                                |
| :--------- | ---------------------------------------- | :------: | ---------------------------------------- |
| rectype    | Record type                              |    No    | All entries = H                          |
| year       | Census year                              |    No    | All entries = 2010                       |
| datanum    | Data set number                          |    No    | All entries = 1                          |
| serial     | Household serial number                  |   Yes    |                                          |
| numprec    | Number of person records following       |    No    | Count value. Not relevant because we have all household-person entries. |
| subsamp    | Subsample number                         |    No    | Used to create representative subsamples. Not relevant. |
| hhwt       | Household weight                         |   Yes    |                                          |
| hhtype     | Household type                           |    No    | Categories not useful.                   |
| repwt      | Household replicate weights              |    No    | Used to generate empirically derived standard errors. Not relevant. |
| cluster    | Household cluster for variance estimation |    No    | Used for Taylor series linear approximation. Not relevant. |
| adjust     | Adjustment factor, ACS/PRCS              |    No    | Adjustment factor for $ values. Not relevant for single census extract. |
| cpi99      | CPI-U adjustment factor to 1999 dollars  |    No    | Adjustment factor for $ values. Not relevant for single census extract. |
| strata     | Household strata for variance estimation |    No    | Used for Taylor series linear approximation. Not relevant. |
| respmode   | Response mode                            |    No    | Technical detail - not relevant.         |
| repwt1-80  | Household replicate weights (80 fields)  |    No    | Used to generate empirically derived standard errors. Not relevant. |

**Household - Geographic Variables**

| Field name  | Field description                        | Included | Rationale                               |
| ----------- | ---------------------------------------- | :------: | --------------------------------------- |
| region      | Census region and division               |    No    | Cardinality is too high.                |
| stateicp    | State (ICPSR code)                       |    No    | Cardinality is too high.                |
| statefip    | State (FIPS code)                        |    No    | Cardinality is too high.                |
| county      | County                                   |    No    | Cardinality is too high.                |
| countyfips  | County (FIPS code)                       |    No    | Cardinality is too high.                |
| metro       | Metropolitan status                      |    No    | Cardinality is too high.                |
| metarea     | Metropolitan area                        |    No    | Cardinality is too high.                |
| metaread    | Metropolitan area                        |    No    | Cardinality is too high.                |
| city        | City                                     |    No    | Cardinality is too high.                |
| cityerr     | Coverage error in CITY variable          |    No    | Cardinality is too high.                |
| citypop     | City population                          |    No    | 27k/35k fields are blank.               |
| puma        | Public Use Microdata Area                |    No    | Cardinality is too high.                |
| pumares2mig | Public Use Microdata Area matching MIGPUMA |    No    | Cardinality is too high.                |
| pumasupr    | Super Public Use Microdata Area          |    No    | Cardinality is too high.                |
| conspuma    | Consistent PUMA, 1980-1990-2000          |    No    | Cardinality is too high.                |
| appal       | Appalachian region                       |    No    | Captured by other variables.            |
| appald      | Appalachian region                       |    No    | Captured by other geographic variables. |
| homeland    | American Indian, Alaska Native, or Native Hawaiian |    No    | Captured by other geographic variables. |
| cntry       | Country                                  |    No    | All entries = USA                       |

**Household - Group Quarters Variables**

| Field name | Field description      | Included | Rationale                 |
| ---------- | ---------------------- | :------: | ------------------------- |
| gq         | Group quarters status  |    No    | Only affects 157 entries. |
| gqtype     | Group quarters type    |    No    | Only affects 177 entries. |
| gqtyped    | Group quarters funding |    No    | Only affects 177 entries. |

**Household - Economic Characteristic Variables**

| Field name | Field description                        | Included | Rationale                                |
| ---------- | ---------------------------------------- | :------: | ---------------------------------------- |
| farm       | Farm status                              |    No    | Only affects 329 entries.                |
| ownershp   | Ownership of dwelling (tenure)           |    No    | Duplicate, included version with more labels. |
| ownershpd  | Ownership of dwelling (tenure)           |   Yes    |                                          |
| mortgage   | First mortgage status                    |   Yes    |                                          |
| mortgag2   | Second mortgage status                   |    No    | Not necessary for mortgage indicator variable. |
| commuse    | Commercial use                           |    No    | Too remove from population of interest.  |
| farmprod   | Sales of farm products                   |    No    | Only affects sub-sample of population.   |
| acrehous   | Acreage of property                      |    No    | Captured by house value.                 |
| mortamt1   | First mortgage monthly payment           |    No    | Not necessary for mortgage indicator variable. |
| mortamt2   | Second mortgage monthly payment          |    No    | Not necessary for mortgage indicator variable. |
| taxincl    | Mortgage payment includes property taxes |    No    | Not necessary for mortgage indicator variable. |
| insincl    | Mortgage payment includes property insurance |    No    | Not necessary for mortgage indicator variable. |
| propinsr   | Annual property insurance cost           |    No    | Too remote from population of interest.  |
| proptx99   | Annual property taxes, 1990              |    No    | Too remote from population of interest.  |
| owncost    | Selected monthly owner costs             |    No    | Duplicate, aggregates other fields.      |
| rent       | Monthly contract rent                    |   Yes    |                                          |
| rentgrs    | Monthly gross rent                       |    No    | Duplicate, based on alternative calculation. |
| rentmeal   | Meals included in rent                   |    No    | Only affects 27 entries.                 |
| condofee   | Monthly condominium fee                  |    No    | Only affects <1500 entries.              |
| moblhome   | Annual mobile home costs                 |    No    | Only affects 371 entries.                |
| costelec   | Annual electricity cost                  |   Yes    |                                          |
| costgas    | Annual gas cost                          |   Yes    |                                          |
| costwatr   | Annual water cost                        |   Yes    |                                          |
| costfuel   | Annual home heating fuel cost            |    No    | Only affects <5000 entries.              |
| hhincome   | Total household income                   |   Yes    |                                          |
| foodstmp   | Food stamp recipiency                    |   Yes    |                                          |
| valueh     | House value                              |   Yes    |                                          |

**Household - Dwelling Characteristic Variables**

| Field name | Field description             | Included | Rationale                       |
| ---------- | ----------------------------- | :------: | ------------------------------- |
| lingisol   | Linguistic isolation          |   Yes    |                                 |
| vacancy    | Vacancy status                |    No    | Blank for all entries.          |
| kitchen    | Kitchen or cooking facilities |    No    | Only <150 no/blank values.      |
| fridge     | Refrigerator                  |    No    | Only <100 no/blank values.      |
| sink       | Sink with faucet              |    No    | Only <100 no/blank values.      |
| stove      | Stove or range                |    No    | Only <300 no/blank values.      |
| rooms      | Number of rooms               |    No    | Use number of bedrooms instead. |
| plumbing   | Plumbing facilities           |    No    | Only <300 no/blank values.      |
| hotwater   | Hot and cold piped water      |    No    | Only <100 no/blank values.      |
| shower     | Bathtub or shower             |    No    | Only <250 no/blank values.      |
| toilet     | Flush toilet                  |    No    | Only <250 no/blank values.      |
| builtyr2   | Age of structure, decade      |    No    | Not inherent to individual.     |
| unitsstr   | Units in structure            |    No    | Not inherent to individual.     |
| bedrooms   | Number of bedrooms            |   Yes    |                                 |

**Household - Appliances, Mechanical, Other Variables**

| Field name | Field description      | Included | Rationale                                |
| ---------- | ---------------------- | :------: | ---------------------------------------- |
| phone      | Telephone availability |    No    | <1k entries with no phone or unreported. |
| fuelheat   | Home heating fuel      |    No    | Not inherent to individual.              |
| vehicles   | Vehicles available     |   Yes    |                                          |

**Household - Household Composition Variables**

| Field name | Field description                        | Included | Rationale                                |
| ---------- | ---------------------------------------- | :------: | ---------------------------------------- |
| nfams      | Number of families in household          |   Yes    |                                          |
| nsubfam    | Number of subfamilies in household       |   Yes    |                                          |
| ncouples   | Number of married couples in household   |    No    | Mixing of zero and N/A values.           |
| nmothers   | Number of mothers in household           |   Yes    |                                          |
| nfathers   | Number of fathers in household           |   Yes    |                                          |
| multgen    | Multigenerational household              |   Yes    |                                          |
| multgend   | Multigenerational household              |    No    | Duplicate, based on alternative classification. |
| cbnsubfam  | Number of subfamilies in household (original Census Bureau classification) |    No    | Duplicate, based on alternative classification. |

**Person - Technical Variables**

| Field name | Field description                    | Included | Rationale                                |
| ---------- | ------------------------------------ | :------: | ---------------------------------------- |
| pernum     | Person number in sample unit         |   Yes    |                                          |
| perwt      | Person weight                        |   Yes    |                                          |
| slwt       | Sample line weight                   |    No    | Technical detail - not relevant.         |
| repwtp     | Person replicate weights             |    No    | Allows users to generate empirically derived standard errors. Not relevant. |
| repwtp1-80 | Person replicate weights (80 fields) |    No    | Used to generate empirically derived standard errors. Not relevant. |

**Person - Family Interrelationship Variables**

| Field name | Field description                        | Included | Rationale                                |
| ---------- | ---------------------------------------- | :------: | ---------------------------------------- |
| famsize    | Number of own family members in household |   Yes    |                                          |
| nchild     | Number of own children in the household  |   Yes    |                                          |
| nchlt5     | Number of own children under age 5 in household |    No    | Correlated with previous field.          |
| famunit    | Family unit membership                   |    No    | 33k/35k are 1.                           |
| eldch      | Age of eldest own child in household     |    No    | Too remote, concentrate on number of children. |
| yngch      | Age of youngest own child in household   |    No    | Too remote, concentrate on number of children. |
| nsibs      | Number of own siblings in household      |    No    | Too remote, concentrate on number of children. |
| momloc     | Mother's location in the household       |   Yes    |                                          |
| stepmom    | Probable step/adopted mother             |    No    | Probabilistic - accuracy isn't certain.  |
| momrule    | Rule for linking mother                  |    No    | Technical detail - not relevant.         |
| poploc     | Father's location in the household       |   Yes    |                                          |
| steppop    | Probable step/adopted father             |    No    | Probabilistic - accuracy isn't certain.  |
| poprule    | Rule for linking father                  |    No    | Technical detail - not relevant.         |
| sploc      | Spouse's location in household           |   Yes    |                                          |
| sprule     | Rule for linking spouse                  |    No    | Technical detail - not relevant.         |
| subfam     | Subfamily membership                     |    No    | Duplicate with famunit field.            |
| sftype     | Subfamily type                           |    No    | Too remote from research question.       |
| sfrelate   | Relationship within subfamily            |    No    | Too remote from research question.       |
| cbsubfam   | Subfamily number (original Census Bureau classification) |    No    | Duplicate, based on alternative classification. |
| cbsftype   | Subfamily type (original Census Bureau classification) |    No    | Duplicate, based on alternative classification. |
| cbsfrelate | Subfamily relationship (original Census Bureau classification) |    No    | Duplicate, based on alternative classification. |

**Person - Demographic Variables**

| Field name | Field description                  | Included | Rationale                                |
| ---------- | ---------------------------------- | :------: | ---------------------------------------- |
| relate     | Relationship to household head     |    No    | Not relevant because we are not explicitly linking records. |
| related    | Relationship to household head     |    No    | Not relevant because we are not explicitly linking records. |
| sex        | Sex                                |    No    | Already used at pre-processing to create female indicator. |
| age        | Age                                |   Yes    |                                          |
| birthqtr   | Quarter of birth                   |    No    | Not relevant.                            |
| marst      | Marital status                     |   Yes    |                                          |
| birthyr    | Year of birth                      |    No    | Use age field.                           |
| marrno     | Times married                      |    No    | Use marital status field.                |
| marrinyr   | Married within the past year       |    No    | Only relates to census year.             |
| yrmarr     | Year married                       |    No    | Too remote from research question.       |
| divinyr    | Divorced in the past year          |    No    | Only relates to census year.             |
| widinyr    | Widowed in the past year           |    No    | Only relates to census year.             |
| fertyr     | Children born within the last year |    No    | Only relates to census year.             |

**Person - Race, Ethnicity, and Nativity Variables**

| Field name | Field description                       | Included | Rationale                                |
| ---------- | --------------------------------------- | :------: | ---------------------------------------- |
| race       | Race                                    |    No    | Use binary variables below.              |
| raced      | Race                                    |    No    | Use binary variables below.              |
| hispan     | Hispanic origin                         |   Yes    |                                          |
| hispand    | Hispanic origin                         |    No    | Don't need additional fields to create indicator. |
| bpl        | Birthplace                              |   Yes    |                                          |
| bpld       | Birthplace                              |    No    | Don't need additional fields to create indicator. |
| ancestr1   | Ancestry, first response                |    No    | Use race variables below instead.        |
| ancestr1d  | Ancestry, first response                |    No    | Use race variables below instead.        |
| ancestr2   | Ancestry, second response               |    No    | Use race variables below instead.        |
| ancestr2d  | Ancestry, second response               |    No    | Use race variables below instead.        |
| citizen    | Citizenship status                      |   Yes    |                                          |
| yrnatur    | Year naturalized                        |    No    | Only affects sub-sample of population.   |
| yrimmig    | Year of immigration                     |   Yes    |                                          |
| yrsusa1    | Years in the United States              |    No    | Only affects sub-sample of population.   |
| yrsusa2    | Years in the United States, intervalled |    No    | Only affects sub-sample of population.   |
| language   | Language spoken                         |   Yes    |                                          |
| languaged  | Language spoken                         |    No    | Don't need additional categories to create indicator. |
| speakeng   | Speaks English                          |   Yes    |                                          |
| tribe      | Tribe                                   |    No    | Only affects 233 entries.                |
| tribed     | Tribe                                   |    No    | Only affects 233 entries.                |
| racesing   | Race: Single race identification        |    No    | Focus on indicator fields below.         |
| racesingd  | Race: Single race identification        |    No    | Focus on indicator fields below.         |
| racamind   | Race: American Indian or Alaska Native  |   Yes    |                                          |
| racasian   | Race: Asian                             |   Yes    |                                          |
| racblk     | Race: black or African American         |   Yes    |                                          |
| racpacis   | Race: Pacific Islander                  |   Yes    |                                          |
| racwht     | Race: white                             |   Yes    |                                          |
| racother   | Race: some other race                   |   Yes    |                                          |
| racnum     | Number of major race groups             |    No    | Too remote from research question.       |

**Person - Health Insurance Variables**

| Field name | Field description                        | Included | Rationale                                |
| ---------- | ---------------------------------------- | :------: | ---------------------------------------- |
| hcovany    | Any health insurance coverage            |   Yes    |                                          |
| hcovpriv   | Private health insurance coverage        |    No    | Duplicate field, captured in hcovany.    |
| hinsemp    | Health insurance through employer/union  |    No    | Duplicate field, captured in hcovany.    |
| hinspur    | Health insurance purchased directly      |    No    | Duplicate field, captured in hcovany.    |
| hinstri    | Health insurance through TRICARE         |    No    | Duplicate field, captured in hcovany.    |
| hcovpub    | Public health insurance coverage         |    No    | Duplicate field, captured in hcovany.    |
| hinscaid   | Health insurance through Medicaid        |    No    | Duplicate field, captured in hcovany.    |
| hinscare   | Health insurance through Medicare        |    No    | Duplicate field, captured in hcovany.    |
| hinsva     | Health insurance through VA              |    No    | Duplicate field, captured in hcovany.    |
| hinsihs    | Health insurance through Indian Health Services |    No    | Duplicate field, captured in hcovany.    |
| hiufpgbase | Federal poverty guidelines (base)        |    No    | Reference value - doesn't relate to specific person. |
| hiufpginc  | Federal poverty guidelines (increment)   |    No    | Reference value - doesn't relate to specific person. |
| hiurule    | HIU pointer rule                         |    No    | Reference value - doesn't relate to specific person. |
| hiuid      | HIU identification                       |    No    | Reference value - doesn't relate to specific person. |
| hiunpers   | HIU number of persons                    |    No    | Reference value - doesn't relate to specific person. |

**Person - Education Variables**

| Field name | Field description        | Included | Rationale                                |
| ---------- | ------------------------ | :------: | ---------------------------------------- |
| school     | School attendance        |   Yes    |                                          |
| educ       | Educational attainment   |    No    | Duplicate, included version with more labels. |
| educd      | Educational attainment   |   Yes    |                                          |
| gradeatt   | Grade level attending    |    No    | Duplicate, included version with more labels. |
| gradeattd  | Grade level attending    |   Yes    |                                          |
| schltype   | Public or private school |   Yes    |                                          |
| degfield   | Field of degree          |    No    | Already used at pre-processing to create STEM indicator. |
| degfieldd  | Field of degree          |    No    | Already used at pre-processing to create STEM indicator. |
| degfield2  | Field of degree (2)      |    No    | Already used at pre-processing to create STEM indicator. |
| degfield2d | Field of degree (2)      |    No    | Already used at pre-processing to create STEM indicator. |

**Person - Work Variables**

| Field name | Field description                   | Included | Rationale                                |
| ---------- | ----------------------------------- | :------: | ---------------------------------------- |
| empstat    | Employment status                   |   Yes    |                                          |
| empstatd   | Employment status                   |    No    | Duplicate, don't need additional detail as will convert to indicator. |
| labforce   | Labor force status                  |    No    | Captured by empstat.                     |
| occ        | Occupation                          |   Yes    |                                          |
| occ1950    | Occupation, 1950 basis              |    No    | Duplicate field based on alternative classification basis. |
| occ1990    | Occupation, 1990 basis              |    No    | Duplicate field based on alternative classification basis. |
| occ2010    | Occupation, 2010 basis              |    No    | Duplicate field based on alternative classification basis. |
| ind        | Industry                            |    No    | Used occ instead, as captures nature of work rather than industry. |
| ind1950    | Industry, 1950 basis                |    No    | Duplicate field based on alternative classification basis. |
| ind1990    | Industry, 1990 basis                |    No    | Duplicate field based on alternative classification basis. |
| classwkr   | Class of worker                     |    No    | Duplicate, included version with more labels. |
| classwkrd  | Class of worker                     |   Yes    |                                          |
| occsoc     | Occupation, SOC classification      |    No    | Duplicate field based on alternative classification basis. |
| indnaics   | Industry, NAICS classification      |    No    | Duplicate field based on alternative classification basis. |
| wkswork2   | Weeks worked last year, intervalled |    No    | Too remote from research question.       |
| uhrswork   | Usual hours worked per week         |    No    | Too remote from research question.       |
| absent     | Absent from work last week          |    No    | Too remote from research question.       |
| looking    | Looking for work                    |    No    | Too remote from research question.       |
| availble   | Available for work                  |    No    | Too remote from research question.       |
| wrkrecal   | Informed of work recall             |    No    | Too remote from research question.       |
| workedyr   | Worked last year                    |    No    | Too remote from research question.       |

**Person - Income Variables**

| Field name | Field description                     | Included | Rationale                                |
| ---------- | ------------------------------------- | :------: | ---------------------------------------- |
| inctot     | Total personal income                 |   Yes    |                                          |
| ftotinc    | Total family income                   |    No    | Captured by personal and household income fields. |
| incwage    | Wage and salary income                |    No    | Captured by personal and household income fields. |
| incbus00   | Business and farm income, 2000        |    No    | Captured by personal and household income fields. |
| incss      | Social Security income                |    No    | Captured by personal and household income fields. |
| incwelfr   | Welfare (public assistance) income    |    No    | Captured by personal and household income fields. |
| incinvst   | Interest, dividend, and rental income |    No    | Captured by personal and household income fields. |
| incretir   | Retirement income                     |    No    | Captured by personal and household income fields. |
| incsupp    | Supplementary Security Income         |    No    | Captured by personal and household income fields. |
| incother   | Other income                          |    No    | Captured by personal and household income fields. |
| incearn    | Total personal earned income          |    No    | Captured by personal and household income fields. |
| poverty    | Poverty status                        |   Yes    |                                          |

**Person - Occupational Standing Variables**

| Field name | Field description                        | Included | Rationale                                |
| ---------- | ---------------------------------------- | :------: | ---------------------------------------- |
| occscore   | Occupational income score                |    No    | Captured by other work and income fields. |
| sei        | Duncan Socioeconomic Index               |    No    | Captured by other work and income fields. |
| hwsei      | Socioeconomic Index, Hauser and Warren   |    No    | Captured by other work and income fields. |
| presgl     | Occupational prestige score, Siegel      |    No    | Captured by other work and income fields. |
| prent      | Occupational prestige score, Nakao and Treas |    No    | Captured by other work and income fields. |
| erscor50   | Occupational earnings score, 1950 basis  |    No    | Captured by other work and income fields. |
| erscor90   | Occupational earnings score, 1990 basis  |    No    | Captured by other work and income fields. |
| edscor50   | Occupational education score, 1950 basis |    No    | Captured by other work and income fields. |
| edscor90   | Occupational education score, 1990 basis |    No    | Captured by other work and income fields. |
| npboss50   | Nam-Powers-Boyd occupational status score, 1950 basis |    No    | Captured by other work and income fields. |
| npboss90   | Nam-Powers-Boyd occupational status score, 1990 basis |    No    | Captured by other work and income fields. |

**Person - Migration Variables**

| Field name | Field description                        | Included | Rationale                                |
| ---------- | ---------------------------------------- | :------: | ---------------------------------------- |
| migrate1   | Migration status, 1 year                 |    No    | Duplicate, included version with more labels. |
| migrate1d  | Migration status, 1 year                 |   Yes    |                                          |
| migplac1   | State or country of residence 1 year ago |    No    | Cardinality is too high.                 |
| migmet1    | Metropolitan area of residence 1 year ago |    No    | Cardinality is too high.                 |
| migtype1   | Metropolitan status 1 year ago           |    No    | Cardinality is too high.                 |
| migcity1   | City of residence 1 year ago             |    No    | Cardinality is too high.                 |
| migpums1   | Super-PUMA of residence 1 year ago       |    No    | Cardinality is too high.                 |
| migpuma1   | PUMA of residence 1 year ago             |    No    | Cardinality is too high.                 |
| movedin    | When occupant moved into residence       |    No    | 24k/35k values are N/A.                  |

**Person - Disability Variables**

| Field name | Field description             | Included | Rationale |
| ---------- | ----------------------------- | :------: | --------- |
| vetdisab   | Cognitive difficulty          |   Yes    |           |
| diffrem    | Cognitive difficulty          |   Yes    |           |
| diffphys   | Ambulatory difficulty         |   Yes    |           |
| diffmob    | Independent living difficulty |   Yes    |           |
| diffcare   | Self-care difficulty          |   Yes    |           |
| diffsens   | Vision or hearing difficulty  |   Yes    |           |
| diffeye    | Vision difficulty             |   Yes    |           |
| diffhear   | Hearing difficulty            |   Yes    |           |

**Person - Veteran Status Variables**

| Field name | Field description                        | Included | Rationale                                |
| ---------- | ---------------------------------------- | :------: | ---------------------------------------- |
| vetstat    | Veteran status                           |    No    | Duplicate, included version with more labels. |
| vetstatd   | Veteran status                           |   Yes    |                                          |
| vet01ltr   | Veteran, served 2001 or later            |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vet90x01   | Veteran, served 1990-2001                |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vet75x90   | Veteran, served May 1975 to July 1990    |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vet80x90   | Veteran, served 1980 to 1990             |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vet75x80   | Veteran, served 1975 to 1980             |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vetvietn   | Veteran, served during Vietnam era       |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vet55x64   | Veteran, served 1955 to 1964             |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vetkorea   | Veteran, served during Korean conflict era |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vet47x50   | Veteran, served 1947-1950                |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vetwwii    | Veteran, served during WWII era          |    No    | Only affects sub-sample of population. Captured by vetstat field. |
| vetother   | Veteran of other period                  |    No    | Only affects sub-sample of population. Captured by vetstat field. |

**Person - Place of Work & Travel Time Variables**

| Field name | Field description                        | Included | Rationale                              |
| ---------- | ---------------------------------------- | :------: | -------------------------------------- |
| pwstate2   | Place of work: state, 1980 onward        |    No    | Cardinality is too high.               |
| pwmetro    | Place of work: metropolitan area         |    No    | Cardinality is too high.               |
| pwcity     | Place of work: city                      |    No    | Cardinality is too high.               |
| pwtype     | Place of work: metropolitan status       |    No    | Cardinality is too high.               |
| pwpuma00   | Place of work: metropolitan status, 2000 |    No    | Cardinality is too high.               |
| pwpumas    | Place of work: PUMA                      |    No    | Cardinality is too high.               |
| tranwork   | Means of transportation to work          |    No    | Dubious association.                   |
| carpool    | Carpooling                               |    No    | Only affects sub-sample of population. |
| riders     | Vehicle occupancy                        |    No    | Only affects sub-sample of population. |
| trantime   | Travel time to work                      |    No    | Only affects sub-sample of population. |
| departs    | Time of departure for work               |    No    | Only affects sub-sample of population. |
| arrives    | Time of arrival at work                  |    No    | Only affects sub-sample of population. |

**Person - Other Variables**

| Field name | Field description                        | Included | Rationale                               |
| ---------- | ---------------------------------------- | :------: | --------------------------------------- |
| gchouse    | Own grandchildren living in household    |    No    | 17k/35k values blank.                   |
| gcmonths   | Months responsible for grandchildren     |    No    | 34k/35k values blank.                   |
| gcrespon   | Responsible for grandchildren            |    No    | 34k/35k values blank.                   |
| probai     | Probability of American Indian race response |    No    | Probabilistic - accuracy isn't certain. |
| probapi    | Probability of Asian/Pacific Islander race response |    No    | Probabilistic - accuracy isn't certain. |
| probblk    | Probability of black race response       |    No    | Probabilistic - accuracy isn't certain. |
| proboth    | Probability of 'other race' race response |    No    | Probabilistic - accuracy isn't certain. |
| probwht    | Probability of white race response       |    No    | Probabilistic - accuracy isn't certain. |

***

**Data source:** Steven Ruggles, J. Trent Alexander, Katie Genadek, Ronald Goeken, Matthew B. Schroeder, and Matthew Sobek. Integrated Public Use Microdata Series: Version 5.0 [Machine-readable database]. Minneapolis, MN: Minnesota Population Center [producer and distributor], 2010.