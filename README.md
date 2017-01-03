# jobsbox
Python script to apply for jobs from whoishiring.io

### Dependencies
requests - `pip install requests`  
pyyaml - `pip install pyyaml`  
gmail - `pip install gmail`  

### Run
**Edit `config.yml` to fit your needs**
- `use_email_file`: if you want to keep track of who has been emailed so they aren't emailed multiple times
- `password`: text file that has your gmail password
- `categories`: what keywords you want to search on 
  - `email_primary`: what to say for the most-encountered category
  - `email_secondary`: smaller blurb if this category has not been mentioned as much as others. All `email_secondary` fields are comma separated
  
- `email`
  - `from`: your gmail address
  - `subject`, `body`: template for emails. Intersperse with `{ site }`, `{ company }`, `{ email_primary }`, and `{ email_secondary }` as desired and they will be replaced dynamically
  
Optionally set up a cron job to have it run regularly  
`crontab -e`  
`30 12  * * *   cd /path/to/jobsbox/ && .//path/to/jobsbox/Scraper.py`
-> will run everyday at 12:30
