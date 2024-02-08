### INSERT site

USE defaultdatabase;
INSERT INTO site (SiteID, SiteName, SiteType, City, Country, Continent, SafetyRating, SafetyComment, TravelRequirementComments, DescriptionField)
VALUES (NULL, '<text>', '<text>', '<text>', '<text>', '<text>', *, '<text>', '<text>', '<text>');

>or omit SafetyRating, SafetyComment, TravelRequirementComments

USE defaultdatabase;
INSERT INTO site (SiteID, SiteName, SiteType, City, Country, Continent, DescriptionField)
VALUES (NULL, '<text>', '<text>', '<text>', '<text>', '<text>', '<text>');


### INSERT user

USE defaultdatabase;
INSERT INTO user (UserName, UserType, PasswordHash, UserID)
VALUES ('<text>', '<text>', '<text>', NULL);
>UserTypes include: User, Admin, Anonymous

### INSERT review

> omit the date

USE defaultdatabase;
INSERT INTO review (ReviewID, Review, SiteID, UserID)
VALUES (NULL, '<text>', *, *);


### INSERT saved

USE defaultdatabase;
INSERT INTO saved (SiteID, UserID)
VALUES (*, *);


### INSERT event

USE defaultdatabase;
INSERT INTO event (EventID, EventType, EventName, EventStartDate, EventEndDate, EventDescription, SiteID)
VALUES (NULL, '<text>', '<text>', 'YYYY-MM-DD', 'YYYY-MM-DD', '<text>', *);

>EventTypes include Cultural, Recreational, Educational, Sightseeing, Cuisine/Foodational, Charity
