**Created:** 02.12.25, 04:37

**Status:** #

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# C++ Time & Date Datatypes

## Different time Datatypes

- There are 2 different data types that used to store the date and time
	- `time_t` $\Rightarrow$ **time stamps**
	- `struct tm` $\Rightarrow$ **date time structures**

- **Time stamps** 
	- represent a moment in time as a single number
	- makes it easier for the computer to do calculations

- **Date time structures**
	- Structures that represent different components of the date and time as members
	- This makes it easier for us to specify dates
	- Date time structures have the following members
		- `tm_sec` - The seconds within a minute
		- `tm_min` - The minutes within an hour
		- `tm_hour` - The hour within a day (from 0 to 23)
		- `tm_mday` - The day of the month
		- `tm_mon` - The month (from 0 to 11 starting with January)
		- `tm_year` - The number of years since 1900
		- `tm_wday` - The weekday (from 0 to 6 starting with Sunday)
		- `tm_yday` - The day of the year (from 0 to 365 with 0 being January 1)
		- `tm_isdst` - Positive when daylight saving time is in effect, zero when not in effect and negative when unknown

## Creating Time Stamps

- `time()` function can only create a timestamp for the current date

- `mktime()` function can create a timestamp for any date
	- `mktime()` function converts a date-time structure into a timestamp
	- The `mktime()` function needs these members to have a value: 
		- `tm_year`, `tm_mon`, `tm_mday`, `tm_hour`, `tm_min`, `tm_sec`, `tm_isdst`

#### Example

- Creating a timestamp using `mktime()` function
```cpp
struct tm datetime;
time_t timestamp;

tm datetime = {};
datetime.tm_year = 2025 - 1900; // Number of years since 1900
datetime.tm_mon = 12 - 1; // Number of months since January (months are 0-indexed)
datetime.tm_mday = 17;
datetime.tm_hour = 12;
datetime.tm_min = 30;
datetime.tm_sec = 1;
// Daylight Savings must be specified
// -1 uses the computer's timezone setting
datetime.tm_isdst = -1;

timestamp = mktime(&datetime);

cout << ctime(&timestamp);
```

## Creating Date Time Structures

- `mktime()` also fills in the `tm_wday` and `tm_yday` members of the date-time structure with the correct values

# References


## Closely Related Notes

### Next:

### Prev:
