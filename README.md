# collegedata
Information compiled about various universities into JSON documents for easy programmatic perusal.

I compiled these by hand from the Common Data Sets of various colleges. Please be nice.

# Format

- `name`: Full name of the college.
- `last_cds`: Last Common Data Set year the information was pulled from. The latest, 2015-2016, would be `2016`. 2014-2015 would be `2015`.

## `location`
Info about the location of the college

- `city`: Name of the city the college is located in.
- `state`: Two letter state code of the state the college is located in.
- `lat`: Latitude of the college. (According to Google Maps)
- `lon`: Longitude of the college. (According to Google Maps)

## `info`
General info about the college

- `institution_control`: Whether the institution is `PUBLIC` (Public), `PRIVATE` (Private not-for-profit), or `PROFIT` (Avoid).
- `classification`: Whether the institution is `COED` (Coed), `MENS` (Men's college), or `WOMENS` (Women's college).
- `academic_calendar`: What academic calendar the institution uses, which can be `SEMESTER` (semester calendar), `QUARTER` (quarter calendar), `TRIMESTER` (trimester calendar), `FOUR_ONE_FOUR` (4-1-4 calendar), `CONTINUOUS` (continuous calendar), or `OTHER`.
- `degrees_offered`: A list of the degrees offered at the instutition, which can contain any of the following: `CERTIFICATE`, `DIPLOMA`, `ASSOCIATE`, `TRANSFER_ASSOCIATE`, `TERMINAL_ASSOCIATE`, `BACHELORS`, `POSTBACHELORS_CERTIFICATE`, `MASTERS`, `POSTMASTERS_CERTIFICATE`, `DOCTORAL_RESEARCH`, `DOCTORAL_PROFESSIONAL`, `DOCTORAL_OTHER`.

## `enrollment`
Information about the enrollment at the college.

- `retention_rate`: A number (0-1) representing the percentage of students remaining at the school after a year.

### `count`
Information about the number of enrolled students at the college.

- `total_undergraduate`: Total number of undergraduate students enrolled at the college.
- `total_graduate`: Total number of graduate students enrolled at the college.
- `total`: Total number of students enrolled at the college.

#### `full_time`
Information about the number of full-time enrolled students at the college.

##### `undergraduate`
Information about the number of undergraduate full-time enrolled students at the college.

- `degree_seeking_first_time_total`: Total number of students who fall under "Degree seeking, first time freshmen."
- `degree_seeking_first_time_men`: Total number of men who fall under "Degree seeking, first time freshmen."
- `degree_seeking_first_time_women`: Total number of women who fall under "Degree seeking, first time freshmen."

- `degree_seeking_first_year_other_total`: Total number of students who fall under "Other first year, degree seeking students."
- `degree_seeking_first_year_other_men`: Total number of men who fall under "Other first year, degree seeking students."
- `degree_seeking_first_year_other_women`: Total number of women who fall under "Other first year, degree seeking students."

- `degree_seeking_other_total`: Total number of students who fall under "All other degree seeking."
- `degree_seeking_other_men`: Total number of men who fall under "All other degree seeking."
- `degree_seeking_other_women`: Total number of women who fall under "All other degree seeking."

- `degree_seeking_total`: Total number of students who fall under "Degree seeking."
- `degree_seeking_men`: Total number of men who fall under "Degree seeking."
- `degree_seeking_women`: Total number of women who fall under "Degree seeking."

- `other_enrolled_total`: Total number of students who fall under "Other undergraduate students enrolled in for-credit courses."
- `other_enrolled_men`: Total number of men who fall under "Other undergraduate students enrolled in for-credit courses."
- `other_enrolled_women`: Total number of women who fall under "Other undergraduate students enrolled in for-credit courses."

- `total`: Total number of undergraduate full-time enrolled students at the college.
- `total_men`: Total number of undergraduate full-time enrolled men at the college.
- `total_women`: Total number of undergraudate full-time enrolled women at the college.

##### `graduate`
Information about the number of graduate full-time enrolled students at the college.

- `degree_seeking_first_time_total`: Total number of students who fall under "Degree seeking, first time."
- `degree_seeking_first_time_men`: Total number of men who fall under "Degree seeking, first time."
- `degree_seeking_first_time_women`: Total number of women who fall under "Degree seeking, first time."

- `degree_seeking_other_total`: Total number of students who fall under "All other degree seeking."
- `degree_seeking_other_men`: Total number of men who fall under "All other degree seeking."
- `degree_seeking_other_women`: Total number of women who fall under "All other degree seeking."

- `other_enrolled_total`: Total number of students who fall under "Other graduate students enrolled in for-credit courses."
- `other_enrolled_men`: Total number of men who fall under "Other graduate students enrolled in for-credit courses."
- `other_enrolled_women`: Total number of women who fall under "Other graduate students enrolled in for-credit courses."

- `total`: Total number of graduate full-time enrolled students at the college.
- `total_men`: Total number of graduate full-time enrolled men at the college.
- `total_women`: Total number of graudate full-time enrolled women at the college.

#### `part_time`
Information about the number of part-time enrolled students at the college.

This section follows the exact same format as the `full_time` section above, containing all the exact same fields, except defined in the context of part_time students. I really don't feel like retyping it adds anything. So I'm not going to.

### `count_by_origin`
Information about the number of enrolled students at the college, categorized by race/ethnicity.

#### `freshmen`
Information about the number of enrolled degree seeking, first time, first year students enrolled at the college, categorized by race/ethnicity.

- `nonresident`: Number of "Nonresident Alien" DSFT students enrolled at the college. (Generally means International students.)
- `hispanic`: Number of Hispanic/Latino DSFT students enrolled at the college.
- `black`: Number of Black/African-American DSFT students enrolled at the college. Note that hispanic students are counted under `hispanic`, even if they're half hispanic half black, because most colleges desparately need to fluff their hispanic stats. Which is weird.
- `white`: Number of White DSFT students enrolled at the college. Generally the biggest number.
- `american_indian`: Number of American Indian or Alaska Native students enrolled at the college.
- `asian`: Number of Asian students enrolled at the college.
- `pacific`: Number of Native Hawaiian or other Pacific Islander DSFT students enrolled at the college.
- `bi`: Number of DSFT students with "two or more races," unless they're hispanic, in which case they fall under `hispanic`.
- `other`: Number of DSFT students enrolled at the college who did not mark an ethnicity or do not know their ethnicity.

#### `ds_undergraduate`
Information about the number of enrolled degree seeking undergraduate students at the college, categorized by race/ethnicity.

Contains all the same fields as `freshmen`, above.

#### `total_undergraduate`
Information about the number of enrolled undergraduate students at the college, categorized by race/ethnicity.\

Contains all the same fields as `freshmen`, above.

### `count_degrees`
Number of degrees awarded in th last academic year.

Categorized by degree type, as listed in `info.degrees_offered`

- `CERTIFICATE`
- `DIPLOMA`
- `ASSOCIATE`
- `TRANSFER_ASSOCIATE`
- `TERMINAL_ASSOCIATE`
- `BACHELORS`
- `POSTBACHELORS_CERTIFICATE`
- `MASTERS`
- `POSTMASTERS_CERTIFICATE`
- `DOCTORAL_RESEARCH`
- `DOCTORAL_PROFESSIONAL`
- `DOCTORAL_OTHER`

## `admission`
Information about the admission process at the college.

- `diploma_required`: `NO` - The college does not require a high school diploma. `YES` - The college requires a high school diploma. `YES_OR_GED` - The college requires either a high school diploma or a GED. (C3)
- `college_prep_required`: `NO` - The college does not require a college-preparatory program. `RECCOMEND` - The college reccomends, but does not require, prospective students take a college-preparatory program. `YES` - The college requires students to take a college-preparatory program. (C4)

### `ftfy`
Information about the first time, first year applicants at the college. (C1)

- `applicants_men`: Number of men who applied to the school.
- `applicants_women`: Number of women who applied to the school.

- `accepted_men`: Number of men who were accepted to the school.
- `accepted_women`: Number of women who were accepted to the school.

- `enrolled_men`: Number of full-time men who enrolled at the school.
- `enrolled_women`: Number of full-time women who enrolled at the school.

- `enrolled_part_time_men`: Number of part-time men who enrolled at the school.
- `enrolled_part_time_women`: Number of part-time women who enrolled at the school.

### `waitlist`
Information about the waitlist at the college. (C2)

- `policy`: Boolean - does the college have a waitlist policy?
- `ranked`: Boolean - is the waitlist ranked?
- `offered`: Number of students offered a spot on the waitlist.
- `accepted`: Number of students accepting a spot on the waitlist.
- `admitted`: Number of students admitted from the waitlist.

### `factors`
Information about the importance of certain factors in the application process.

All factors are graded 0-3, 0 being Not Considered, 1 being Considered, 2 being Important, and 3 being Very Important.

- `rigor`: Rigor of secondary school record
- `rank`: Class rank
- `gpa`: Academic GPA
- `tests`: Standardized Test Scores
- `essay`: Application Essay
- `reccomendations`: Reccomendations
- `interview`: Interview
- `extracurricular`: Extracurricular activities
- `talent`: Talent/Ability
- `character`: Character/Personal Qualities
- `firstgen`: First generation
- `alumni`: Alumni/ae relation
- `residence`: Geographical residence
- `state`: State residency
- `religion`: Religious affiliation
- `race`: Race/Ethnicity
- `volunteer`: Volunteer work
- `work`: Work experience
- `interest`: Level of applicant interest

### `tests`
Information about test scores in admitted students.

- `used`: Boolean - does this college consider standardized tests?
- `required`: Boolean - does this college require the SAT OR ACT to be submitted?

