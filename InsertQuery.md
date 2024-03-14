### INSERT site

USE defaultdatabase;
INSERT INTO site (SiteID, SiteName, SiteType, City, Country, Continent, SafetyRating, SafetyComment, TravelRequirementComments, DescriptionField)
VALUES (NULL, 'DATA', 'DATA', 'DATA', 'DATA', 'DATA', *, 'DATA', 'DATA', 'DATA');

>or omit SafetyRating, SafetyComment, TravelRequirementComments
>Continent includes: North_America, South_America, Africa, Asia, Antarctica, Europe, Australia

USE defaultdatabase;
INSERT INTO site (SiteID, SiteName, SiteType, City, Country, Continent, DescriptionField)
VALUES (NULL, 'DATA', 'DATA', 'DATA', 'DATA', 'DATA', 'DATA');


### INSERT user

USE defaultdatabase;
INSERT INTO user (UserName, UserType, PasswordHash, UserID)
VALUES ('DATA', 'DATA', SHA2('DATA', 256), NULL);
>UserTypes include: User, Admin, Anonymous

### INSERT review

> omit the date

USE defaultdatabase;
INSERT INTO review (ReviewID, Review, SiteID, UserID)
VALUES (NULL, 'DATA', *, *);


### INSERT saved

USE defaultdatabase;
INSERT INTO saved (SiteID, UserID)
VALUES (*, *);


### INSERT event

USE defaultdatabase;
INSERT INTO event (EventID, EventType, EventName, EventStartDate, EventEndDate, EventDescription, SiteID)
VALUES (NULL, 'DATA', 'DATA', 'YYYY-MM-DD', 'YYYY-MM-DD', 'DATA', *);

>EventTypes include Cultural, Recreational, Educational, Sightseeing, Cuisine/Foodational, Charity
