"""
Project for Week 4 of "Python Programming Essentials".
Collection of functions to process dates.

Be sure to read the project description page for further information
about the expected behavior of the program.
"""

import datetime

def days_in_month(year, month):
    """
    Inputs:
      year  - an integer between datetime.MINYEAR and datetime.MAXYEAR
              representing the year
      month - an integer between 1 and 12 representing the month

    Returns:
      The number of days in the input month.
    """
    if month == 12:
        number_of_days = datetime.date(year + 1, 1, 1) - datetime.date(year, month, 1)
        return number_of_days.days
    else:
        number_of_days = datetime.date(year, month + 1, 1) - datetime.date(year, month, 1) 
        return number_of_days.days

def is_valid_date(year, month, day):
    """
    Inputs:
      year  - an integer representing the year
      month - an integer representing the month
      day   - an integer representing the day

    Returns:
      True if year-month-day is a valid date and
      False otherwise
    """
    if year in range(datetime.MINYEAR, datetime.MAXYEAR + 1):
        if month in range(1, 13):
            if day in range(1, days_in_month(year, month) + 1):
                return True
            else: return False
        else: return False
    else:
        return False

def days_between(year1, month1, day1, year2, month2, day2):
    """
    Inputs:
      year1  - an integer representing the year of the first date
      month1 - an integer representing the month of the first date
      day1   - an integer representing the day of the first date
      year2  - an integer representing the year of the second date
      month2 - an integer representing the month of the second date
      day2   - an integer representing the day of the second date

    Returns:
      The number of days from the first date to the second date.
      Returns 0 if either date is invalid or the second date is
      before the first date.
    """
    if is_valid_date(year1, month1, day1) and is_valid_date(year2, month2, day2):
        if datetime.date(year2, month2, day2) > datetime.date(year1, month1, day1):
            number_of_days_between = datetime.date(year2, month2, day2) - datetime.date(year1, month1, day1)
            return number_of_days_between.days
        else: return 0
    else: return 0

def age_in_days(year, month, day):
    """
    Inputs:
      year  - an integer representing the birthday year
      month - an integer representing the birthday month
      day   - an integer representing the birthday day

    Returns:
      The age of a person with the input birthday as of today.
      Returns 0 if the input date is invalid or if the input
      date is in the future.
    """
    if is_valid_date(year, month, day):
        if datetime.date(year, month, day) < datetime.date.today():
            age = days_between(year, month, day, datetime.date.today().year,
                                datetime.date.today().month, datetime.date.today().day)
            return age
        else: return 0
    else: return 0
