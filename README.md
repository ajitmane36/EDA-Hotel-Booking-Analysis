# Hotel Booking Analysis - EDA Using Python and Dashboard Making Using Tableau...

## <ins> Dashboard Link </ins> - [Link](https://public.tableau.com/app/profile/ajit.mane/viz/HBADashboard-AjitMane/HBADashboard)

### <ins> Dashboard Usage <ins>
- To view the dashboard, follow these steps:
  - Clone this repository to your local machine or download the Tableau dashboard file or click the above dashboard link.
  - Open the dashboard file using Tableau Desktop or Tableau Online.
  - Connect the dashboard using the provided dataset given in repository.
  - Explore the different pages and visuals within the dashboard to gain insights.

## <ins> Objective </ins>
#### Our primary goal is to conduct EDA on the provided dataset and derive valuable conclusions about broad hotel booking trends and how various factors interact to affect hotel bookings.
## <ins> Dataset </ins>
     We get a dataset of hotel reservations. A city hotel and a resort hotel's reservations are included in this dataset. It has the following features:
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

## <ins> Data Cleaning and Feature Engineering </ins>
     [1] Removing Duplicate Values
     - Rows that were duplicates were removed.
     [2] Handling Null / Missing Values
     - Children, country, and agent are discrete numerical variables, so replaced null values with mode of it.
     - Variable company had null values greater than 50%, so removed it.
     [3] Removing Outliers
     - Interquartile Range in the skew symmetric curve used to remove outliers found in the lead_time and adr variables.
     [4] Converting Columns to Appropriate Data Types
     - Datatypes of variables "children," "agent," "reservation_status_date," "total_people," and "total_children" were transformed from float64 datatypes to int64.
     - Datatype of the variable "reservation_status_date" was transformed from object datatype to datetime64.
     [5] Created New Columns
     - The variable "total_stays" is created by adding the variables "stays_in_weekend_nights" and "stays_in_weeknights."
     - The variable "total_people" is created by adding the variables "adults," "children," and "babies."
     - The variable "reserved_room_assigned" is made up of the variables "reserved_room_type" and "assigned_room_type."
     - From variables "children" and "babies," a new "total_children" variable is created by adding both of them.
     - The variable "total_people" used to create "guest_category."
     - The variable "lead_time_category" created from the variable "lead_time."
## <ins> Exploratory Data Analysis </ins>
     performed EDA and tried answering the following questions:
     - 1] Is not having a reserved room assigned a reason for booking cancellations?
     - 2]  Is the high lead_time a reason for booking cancellations?
     - 3] How many people are reservations made for?
     - 4] Which hotel type has the most advanced reservations?
     - 5] Which distribution channels have the most cancellations of bookings?
     - 6] Which market segment is most used for booking hotels, and which market segment bookings are most canceled?
     - 7]  Which room generates a higher ADR?
     - 8]  Which hotel type is the busiest?
     - 9] Which month is the busiest for hotels?
     - 10]  Which customer type generates more revenue in terms of hotel types and customer types?
     - 11] In terms of hotel types, how many parking spaces are most frequently requested by customers?
     - 12]  What is the most common number of nights booked by customers?
     - 13] What is the most common number of special requests made by customers, and what kind of customer are they?
     - 14] Is the ADR affected by the hotel not giving a reserved room?
     - 15] The majority of bookings were made for how many people, and the majority of cancellations of bookings were made for how many people?
     - 16] Which country makes the most reservations, and which agent makes the most bookings?
     - 17] Does a longer waiting period cause the cancellation of bookings?

     These following graphs and plots were primarily created using Matplotlib and the Seaborn package.
     - Count plot
     - Bar plot
     - Line plot
     - Box plot
     - Violin plot
     - Kdeplot
     - Heatmap
     - Pairplot

##### <ins>Univariate Analysis</ins>
     performed univariate analysis and reached the following conclusions:
     - A city hotel was most preferred by 61.07 percent of customers over a resort.
     - 72.48% of bookings are not cancelled. Almost one-third of all reservations are canceled. 
     - Bookings increased by 33.28% in 2016 compared to 2015, but fell by 12.25% in 2017.
     - Customers make the most reservations in August, followed by July. Customers made the fewest reservations in November, - December, and January. So we can make offers to customers in November, December, and January to maximise booking.
     - BB is the most requested food.
     - Most of the bookings are made through the online platform.
     - The top distribution channel is TA/TO, which is used to make most of the bookings.
     - The majority of hotel bookings are made by new customers. Very few customers (3.86%) visited again.
     - The customer's top preference is for Room A to be reserved.
     - Customers do not want to pay a pre-deposit for a reservation.
     - Most customers (80%) preferred to book a hotel for a short stay.
     - 90% of people do not require parking spaces for their vehicles.
     - 70% chance that bookings will not be cancelled by customers.
     - Reserved rooms were not assigned to 15% of customers. Ensure that customers receive the rooms they have reserved.
     - Reservations were often made for two people. 10% or so of guests brought their families. Few bring their families with them. Offer family-friendly discounts to encourage reservations for family and business events.
##### <ins> Bivariate Analysis </ins>
     performed bivariate analysis and reached the following conclusions:
     - The inability to assign a reserved room to a customer is not grounds for cancellation
     - Less lead time means fewer cancellations. Booking cancellations are not caused by a longer Lead time.
     - Most customers book hotels for two people (couples). Customers prefer city hotels over resorts for family bookings.
     - In comparison to city hotels, guests book resort hotels a little bit in advance.
     - The majority of canceled bookings were made through the TA/TO distribution channel
     - The majority of hotel reservations are made online, as are the majority of cancellations of reservations made by customers who made their reservations online.
     - Room types G, followed by H, generate high ADR
     - A city hotel is busier than a resort.
     - City hotels generate more revenue (54.86%) than resort hotels (45.14%)
     - Only a few customers (8.31%) requested parking. One parking space is most desirable to customers. 
     - The majority of the guests are staying at the hotel for three nights. 
     - Customers frequently make one special request. Couples make the majority of special requests.
     - Not assigning a reserved room does not affect ADR.
     - The majority of reservations are made through country PRT.
     - Agent nummber 9 made most number of bookings.
     - Longer waiting period is not a reason for booking cancellation.
     - People were consistently interested in booking rooms in advance in 2015, 2016, and 2017.

## <ins> Conclusion </ins>
     - The top country with the most number of bookings is PRT, and the number one agent with the most number of bookings is 9. 
     - Customers favored city hotels more than resort hotels by a margin of 61.07 percent.
     - One of the four reservations is canceled.
     - The most popular food is BB.
     - The Online (internet) platform is used to make the majority of bookings.
     - The majority of the bookings are made using TA/TO, the leading distribution channel.
     - The vast majority of hotel bookings are made by new guests. Almost no consumers (3.86%) returned.
     - The customer wants Room A to be reserved the most.
     - Customers do not wish to make a bookings with a pre-deposit.
     - Customers (80%) favored making a hotel reservation for a short visit.
     - Only 10% of people require space to park their cars.
     - Most visitors are couples.
     - The inability to assign a reserved room to a customer is not grounds for cancellation.
     - Booking cancellations are not caused by a longer Lead time.
     - A city hotel is busier than a resort.
     - The busiest months for hotels are October and September. There isn't a lengthy wait for reservations in July.
     - Not assigning a reserved room does not affect ADR.

## <ins> Challenges </ins>
     - The data contained a large number of duplicates.
     - The improper data type format was used for the data.
     - It was challenging to select the best visualization techniques.
     - The dataset contained a large number of null values.
