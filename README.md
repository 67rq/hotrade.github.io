# hotrade.github.io python
import time
import random

OTC মার্কেট লিস্ট (উদাহরণস্বরূপ)
otc_markets = [
    "USD/JPY", "EUR/USD", "GBP/USD", "AUD/USD", "USD/CAD", 
    "NZD/USD", "USD/CHF", "EUR/GBP", "EUR/JPY", "GBP/JPY"
]

def predict_direction(market):
    # এখানে আসলে মডেল বা API কল থাকবে, এখন র‍্যান্ডম বেছে নিচ্ছি
    return random.choice(["🟢📈 UP", "🔴📉 DOWN"])

def main():
    print("OTC মার্কেট লিস্ট:")
    for i, market in enumerate(otc_markets, 1):
        print(f"{i}. {market}")

    while True:
        choice = input("মার্কেট সিলেক্ট করুন (নাম অথবা নম্বর, বের হতে 'exit' লিখুন): ").strip()
        if choice.lower() == 'exit':
            print("প্রোগ্রাম শেষ করা হলো।")
            break

        # নম্বর বা নাম দিয়ে সিলেকশন চেক
        if choice.isdigit():
            idx = int(choice) -1
            if 0 <= idx < len(otc_markets):
                market = otc_markets[idx]
            else:
                print("ভুল নম্বর, আবার চেষ্টা করুন।")
                continue
        else:
            if choice.upper() in otc_markets:
                market = choice.upper()
            else:
                print("ভুল মার্কেট নাম, আবার চেষ্টা করুন।")
                continue

        print(f"{market} মার্কেটের জন্য প্রেডিকশন করছে...")
