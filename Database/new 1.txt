SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";

-- Database: `sales`
--

DELIMITER $$
--
-- Procedures
--
CREATE DEFINER=`root`@`localhost` PROCEDURE `insertData` (IN `in_username` VARCHAR(40), IN `in_gender` VARCHAR(8), IN `in_mobile` VARCHAR(20), IN `in_email` VARCHAR(20), IN `in_dob` VARCHAR(10), IN `in_joining_date` VARCHAR(10), IN `in_userid` VARCHAR(20))  BEGIN
INSERT INTO users(username, gender, mobile, email, dob, joining_date, userid) VALUES(in_username,in_gender,in_mobile,in_email,in_dob,in_joining_date,in_userid);
END$$

DELIMITER ;
CREATE TABLE `person` (
  `name` varchar(20) NOT NULL,
  `id` varchar(20) NOT NULL PRIMARY KEY,
  `streetName` varchar(40) NOT NULL,
  `state` varchar(15) NOT NULL,
  `city` varchar(15) NOT NULL,
  `zipcode` varchar(20) DEFAULT NULL,
   
) ENGINE=InnoDB DEFAULT CHARSET=latin1 ROW_FORMAT=DYNAMIC;
 
CREATE TABLE `sales` (
  `S_id` varchar(20) NOT NULL,
  `cat.` varchar(20) NOT NULL,
  `spent` varchar(20) NOT NULL,
   FOREIGN KEY (S_id) references person (id)
)ENGINE=InnoDB DEFAULT CHARSET=latin1 ROW_FORMAT=DYNAMIC;
