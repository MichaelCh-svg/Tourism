### INSERT site

USE defaultdatabase;
INSERT INTO site (SiteID, SiteType, City, Country, Continent, SafetyRating, SafetyComment, TravelRequirementComments, DescriptionField)
VALUES (NULL, '*', '*', '*', '*', *, '*', '*', '*');

>or omit SafetyRating, SafetyComment, TravelRequirementComments

USE defaultdatabase;
INSERT INTO site (SiteID, SiteType, City, Country, Continent, DescriptionField)
VALUES (NULL, '*', '*', '*', '*', '*');


### INSERT user

USE defaultdatabase;
INSERT INTO user (UserName, UserType, PasswordHash, UserID)
VALUES ('*', '*', '*', NULL);


### INSERT review

> omit the date
USE defaultdatabase;
INSERT INTO review (ReviewID, Review, SiteID, UserID)
VALUES (*, '*', *, *);


### INSERT saved

USE defaultdatabase;
INSERT INTO saved (SiteID, UserID)
VALUES (*, *);


### INSERT event
USE defaultdatabase;
INSERT INTO event (EventID, EventDescription, SiteID)
VALUES (NULL, '*', *);
