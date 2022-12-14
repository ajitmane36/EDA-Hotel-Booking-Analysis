# Hotel Booking Analysis - EDA
## Objective
#### Our primary goal is to conduct EDA on the provided dataset and derive valuable conclusions about broad hotel booking trends and how various factors interact to affect hotel bookings.
## Dataset
#### We get a dataset of hotel reservations. A city hotel and a resort hotel's reservations are included in this dataset. It has the following features:
- hotel: Name of hotel ( City or Resort)
- is_canceled: Whether the booking is canceled or not (0 for no canceled and 1 for canceled)
- lead_time: time (in days) between booking transaction and actual arrival.
- arrival_date_year: Year of arrival
- arrival_date_month: month of arrival
- arrival_date_week_number: week number of arrival date.
- arrival_date_day_of_month: Day of month of arrival date
- stays_in_weekend_nights: No. of weekend nights spent in a hotel
- stays_in_week_nights: No. of weeknights spent in a hotel
- adults: No. of adults in single booking record.
- children: No. of children in single booking record.
- babies: No. of babies in single booking record. 
- meal: Type of meal chosen 
- country: Country of origin of customers
- market_segment: What segment via booking was made and for what purpose.
- distribution_channel: Via which medium booking was made.
- is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for 
                     Yes)
- previous_cancellations: No. of previous canceled bookings.
- previous_bookings_not_canceled: No. of previous non-canceled bookings.
- reserved_room_type: Room type reserved by a customer.
- assigned_room_type: Room type assigned to the customer.
- booking_changes: No. of booking changes done by customers
- deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
- agent: Id of agent for booking
- company: Id of the company making a booking
- days_in_waiting_list: No. of days on waiting list.
- customer_type: Type of customer(Transient, Group, etc.)
- adr: Average Daily rate.
- required_car_parking_spaces: No. of car parking asked in booking
- total_of_special_requests: total no. of special request.
- reservation_status: Whether a customer has checked out or canceled,or not showed 
- reservation_status_date: Date of making reservation status.

Total 119390 rows and 32 columns in dataset
## Data Cleaning and Feature Engineering
### [1] Removing Duplicate Values
- Rows that were duplicates were removed.
### [2] Handling Null / Missing Values
- Children, country, and agent are discrete numerical variables, so replaced null values with mode of it.
- Variable company had null values greater than 50%, so removed it.
### [3] Removing Outliers
- Interquartile Range in the skew symmetric curve used to remove outliers found in the lead_time and adr variables.
### [4] Converting Columns to Appropriate Data Types
- Datatypes of variables "children," "agent," "reservation_status_date," "total_people," and "total_children" were transformed from float64 datatypes to int64.
- Datatype of the variable "reservation_status_date" was transformed from object datatype to datetime64.
### [5] Created New Columns
- The variable "total_stays" is created by adding the variables "stays_in_weekend_nights" and "stays_in_weeknights."
- The variable "total_people" is created by adding the variables "adults," "children," and "babies."
- The variable "reserved_room_assigned" is made up of the variables "reserved_room_type" and "assigned_room_type."
- From variables "children" and "babies," a new "total_children" variable is created by adding both of them.
- The variable "total_people" used to create "guest_category."
- The variable "lead_time_category" created from the variable "lead_time."
## Exploratory Data Analysis
performed EDA and tried answering the following questions:
