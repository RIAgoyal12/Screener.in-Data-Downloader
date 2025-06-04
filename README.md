# Screener.in Data Downloader

A Python tool to automatically download financial data from Screener.in for multiple companies and export it to Excel files. Perfect for financial analysis, stock research, and portfolio management.

## 🚀 Features

- **Single Company Download**: Get comprehensive financial data for any company
- **Bulk Company Download**: Process multiple companies from a list or Excel file
- **Excel Export**: Automatically organize data into structured Excel files with multiple sheets
- **Login Support**: Optional login for premium features
- **Error Handling**: Robust error handling with detailed logging
- **Google Colab Ready**: Optimized for Google Colab environment with automatic file downloads

## 📊 Data Extracted

The tool extracts comprehensive financial information including:

- **Company Information**: Basic company details and metrics
- **Key Financial Ratios**: P/E ratio, debt-to-equity, ROE, ROA, etc.
- **Financial Tables**: Profit & Loss, Balance Sheet, Cash Flow statements
- **Historical Data**: Multi-year financial performance
- **Valuation Metrics**: Market cap, enterprise value, ratios

## 🛠️ Installation

### Prerequisites

```bash
pip install requests beautifulsoup4 pandas openpyxl
```

### For Google Colab

The script automatically installs required packages:

```python
!pip install requests beautifulsoup4 pandas openpyxl
```

## 📖 Usage

### Basic Usage

```python
# Create downloader instance
downloader = ScreenerDownloader()

# Download single company data
downloader.download_company_data("Reliance Industries")

# Download multiple companies
companies = ["Reliance Industries", "TCS", "Infosys"]
for company in companies:
    downloader.download_company_data(company)
    time.sleep(2)  # Be respectful to the server
```

### With Login (for premium features)

```python
# Login with credentials
downloader = ScreenerDownloader()
downloader.login("your_email@example.com", "your_password")

# Or login interactively
downloader.login()  # Will prompt for credentials
```

### Bulk Download from Excel File

```python
# Upload Excel file with company names and process all
download_from_excel(downloader, "companies.xlsx")
```

## 🗂️ Excel File Format

When uploading an Excel file for bulk processing, ensure your file has:

- A column containing company names
- Supported column names: "company", "company name", "name", "companies", "stock"
- If no matching column is found, the first column will be used

Example Excel structure:
```
| Company Name     |
|------------------|
| Reliance Industries |
| TCS              |
| Infosys          |
| HDFC Bank        |
```

## 📁 Output Structure

Each company's data is saved in a separate Excel file with multiple sheets:

```
Company_Name_data.xlsx
├── Summary (Key ratios and metrics)
├── Company Info (Basic company information)
├── Profit & Loss (Historical P&L data)
├── Balance Sheet (Historical balance sheet)
└── Cash Flow (Historical cash flow)
```

For bulk downloads, all files are organized in a timestamped directory and automatically zipped.

## 🔧 Configuration Options

### Customization

```python
# Custom output filename
downloader.download_company_data("Reliance", "custom_filename.xlsx")

# Process with custom delay between requests
time.sleep(5)  # 5-second delay between companies
```

### Error Handling

The tool includes comprehensive error handling:
- Network connection issues
- Company not found
- Rate limiting protection
- Data parsing errors

## ⚠️ Important Notes

### Rate Limiting
- Always add delays between requests (`time.sleep(2)` minimum)
- Respect Screener.in's terms of service
- Consider using login for better rate limits

### Data Accuracy
- Data is scraped from public pages on Screener.in
- Website structure changes may affect functionality
- Always verify critical data manually

### Legal Compliance
- Use responsibly and in accordance with Screener.in's terms of service
- Data is for personal research and analysis only
- Do not use for commercial redistribution

## 🐛 Troubleshooting

### Common Issues

**"Company not found" error:**
- Try alternative company name formats
- Use exact name as shown on Screener.in
- Check for typos in company names

**Rate limiting:**
- Increase delay between requests
- Consider logging in for better limits
- Process companies in smaller batches

**Data extraction issues:**
- Website structure may have changed
- Check if login is required for specific data
- Verify company exists on Screener.in

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Development Setup

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚖️ Disclaimer

This tool is for educational and research purposes only. Users are responsible for:
- Complying with Screener.in's terms of service
- Using data ethically and legally
- Verifying data accuracy for critical decisions
- Respecting rate limits and website policies

The authors are not responsible for any misuse of this tool or any consequences arising from its use.

## 🔗 Related Links

- [Screener.in](https://www.screener.in) - Source website
- [Python Requests Documentation](https://docs.python-requests.org/)
- [BeautifulSoup Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)

## 📈 Example Use Cases

- **Portfolio Analysis**: Download data for all stocks in your portfolio
- **Sector Research**: Compare companies within the same industry
- **Investment Screening**: Bulk download data for fundamental analysis
- **Academic Research**: Gather data for financial studies and projects
- **Regular Monitoring**: Set up periodic data collection for tracking

---

**⭐ If you find this tool useful, please consider giving it a star on GitHub!**
