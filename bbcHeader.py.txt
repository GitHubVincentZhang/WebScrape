import requests
from bs4 import BeautifulSoup

def scrape_bbc_news():
    # URL of the BBC news archive
    url = "https://www.bbc.com/news"

    # Send a GET request
    response = requests.get(url)
    
    # Parse the HTML content of the page with BeautifulSoup
    soup = BeautifulSoup(response.text, 'html.parser')
    
    # Find all headline elements
    headlines = soup.find_all('h3')
    
    # Extract text from each headline and print
    for headline in headlines:
        print(headline.get_text().strip())

if __name__ == "__main__":
    scrape_bbc_news()