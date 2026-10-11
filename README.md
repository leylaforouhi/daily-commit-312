
def calculate_reading_stats(pages_per_day, days):
    total_pages = sum(pages_per_day)
    active_days = sum(1 for pages in pages_per_day if pages > 0)

    average = total_pages / days if days > 0 else 0

    return {
        "total_pages": total_pages,
        "active_days": active_days,
        "average_per_day": round(average, 2),
    }


if __name__ == "__main__":
    daily_pages = [12, 0, 18, 25, 0, 15, 20]
    stats = calculate_reading_stats(daily_pages, len(daily_pages))

    print("Daily pages:", daily_pages)
    print("Total pages:", stats["total_pages"])
    print("Active days:", stats["active_days"])
    print("Daily average:", stats["average_per_day"])
