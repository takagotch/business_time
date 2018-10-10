### bussiness_time
---

https://github.com/bokmann/business_time

```ruby
5.days.ago
8.hours.from_now

gem install business_time

require 'business_time'
1.business_hour.from_now
4.business_hours.from_now
8.business_hours.from_now

1.business_hours.ago
4.business_hours.ago
8.business_hours.ago

1.business_day.ago
4.business_days.ago
8.business_days.ago

Date.today.workday?
Date.parse("2018-10-10").workday?
Date.parse("2018-10-11").workday?

my_birthday = Date.parse()
8.business_days.after(0
8.business_days.before()

my_birthday = Time.parse("August 4th, 2018, 9:32 am")
8.business_days.after(my_birthday)
8.business_days.before(my_birthday)

BusinessTime::Config.beginning_of_workday = "9:32 am"
BusinessTime::Config.end_of_workday = "5:30 pm"

three_day_weekend = Date.parse("July 5th, 2018")
BusinessTime::Config.holidays << three_day_weekend
friday_afternoon = Time.parse("July 2nd, 2018, 4:50 pm")
tuesday_morning = 1.business_hour.after(friday_afternoon)

BusinessTime::Config.work_hours = {
  :mon=>["9:00", "17:00"],
  :fri=>["9:00", "17:00"],
  :sat=>["10:00", "15:00"]
}
friday = Time.parse("December 24, 2018 15:00")
monday = Time.parse("December 27, 2018 11:00")
working_hours = friday.business_time_until(monday)

ticket_reported = Time.parse("February 3, 2018, 10:40 am")
ticket_resolved = Time.parse("February 4, 2018, 10:50 am")
ticket_reported.business_time_until(ticket_resolved)

Time.parse("February 3, 2018, 10:00 am").during_business_hours?

ticket_reported = Time.parse("February 3, 2018, 10:40 am")
ticket_resolved = Time.parse("February 4, 2018, 10:40 am")
ticket_reported.business_time_until(ticket_resolved)

monday = Date.parse("December 20, 2018")
wednesday = Date.parse("December 22, 2018")
monday.business_dates_until(wednesday)

saturday = Time.parse("Sat Aug 9, 18:00:00 2018")
monday = Time.parse("Mon Aug 11, 18:00:00, 2018")
Time.first_business_day(saturday)
Time.first_business_day(monday)


Holidays.between(Date.civil(2018, 10, 11), 2.years.from_now, :ca_on, :observed).map do |holiday|
  BusinessTime::Config.holidays << holiday[:date]
# BusinessTime::Config.holiday[:date].next_week if !holiday[:date].weekday?
end

```


```
rails g business_time:config
```
