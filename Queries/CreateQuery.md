USE defaultdatabase;
CREATE TABLE Site
(
  SiteID SERIAL NOT NULL,
  SiteName VARCHAR(50) NOT NULL,
  SiteType VARCHAR(50) NOT NULL,
  City VARCHAR(50) NOT NULL,
  Country VARCHAR(50) NOT NULL,
  Continent ENUM ('North_America', 'South_America', 'Africa', 'Asia', 'Antarctica', 'Europe', 'Australia'),
  SafetyRating INT,
  SafetyComment VARCHAR(500),
  TravelRequirementComments VARCHAR(500),
  DescriptionField VARCHAR(500) NOT NULL,
  PRIMARY KEY (SiteID)
);

CREATE TABLE Event
(
  EventID SERIAL NOT NULL,
  EventType ENUM ('Cultural', 'Recreational', 'Educational', 'Sightseeing', 'Cuisine', 'Charity'),
  EventName VARCHAR(50),
  EventStartDate DATE,
  EventEndDate DATE,
  EventDescription VARCHAR(500) NOT NULL,
  SiteID BIGINT UNSIGNED NOT NULL,
  PRIMARY KEY (EventID),
  FOREIGN KEY (SiteID) 
REFERENCES Site(SiteID)
ON DELETE CASCADE
	ON UPDATE NO ACTION
);

CREATE TABLE User
(
  UserName VARCHAR(50) NOT NULL,
  UserType ENUM ('Admin', 'User', 'Anonymous'),
  PasswordHash VARCHAR(100) NOT NULL,
  UserID SERIAL NOT NULL,
  PRIMARY KEY (UserID),
  UNIQUE (UserName)
);

CREATE TABLE Saved
(
  SiteID BIGINT UNSIGNED NOT NULL,
  UserID BIGINT UNSIGNED NOT NULL,
  PRIMARY KEY (SiteID, UserID),
  FOREIGN KEY (SiteID) 
REFERENCES Site(SiteID)
ON DELETE CASCADE
ON UPDATE NO ACTION,
  FOREIGN KEY (UserID) 
REFERENCES User(UserID)
ON DELETE CASCADE
	ON UPDATE NO ACTION
);


CREATE TABLE Review
(
  ReviewID SERIAL NOT NULL,
  RDate DATETIME NOT NULL DEFAULT NOW(),
  Review TEXT NOT NULL,
  SiteID BIGINT UNSIGNED NOT NULL,
  UserID BIGINT UNSIGNED NOT NULL,
  PRIMARY KEY (ReviewID),
  FOREIGN KEY (SiteID) 
REFERENCES Site(SiteID)
ON DELETE CASCADE
ON UPDATE NO ACTION,
  FOREIGN KEY (UserID) 
REFERENCES User(UserID)
ON DELETE CASCADE
	ON UPDATE NO ACTION
);

CREATE VIEW SiteSearch AS
Select EventName, EventType, EventDescription, EventStartDate, EventEndDate, 
SiteType, City, Country, Continent, SiteName, S.SiteID, E.EventID
from Site S
LEFT JOIN Event E
ON S.SiteID = E.SiteID
UNION
Select EventName, EventType, EventDescription, EventStartDate, EventEndDate, 
SiteType, City, Country, Continent, SiteName, S.SiteID, E.EventID
from Site S
RIGHT JOIN Event E
ON S.SiteID = E.SiteID;

CREATE VIEW SiteDisplay AS
Select EventName, EventType, EventDescription, EventStartDate, EventEndDate, 
SiteType, City, Country, Continent, SiteName,
SafetyComment, TravelRequirementComments, DescriptionField, S.SiteID, E.EventID
from Site S
LEFT JOIN Event E
ON S.SiteID = E.SiteID
UNION
Select EventName, EventType, EventDescription, EventStartDate, EventEndDate, 
SiteType, City, Country, Continent, SiteName,
SafetyComment, TravelRequirementComments, DescriptionField, S.SiteID, E.EventID
from Site S
RIGHT JOIN Event E
ON S.SiteID = E.SiteID;
