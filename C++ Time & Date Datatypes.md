**Created:** 02.12.25, 04:37

**Status:** #

**Hashtags:**
- 

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# C++ Time & Date Datatypes

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

# References


## Closely Related Notes

### Next:

### Prev:
