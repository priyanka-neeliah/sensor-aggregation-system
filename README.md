# sensor-aggregation-system
# 🚀 SensorFlow: Smart Data Aggregation System

Ever wonder how smart cities handle thousands of sensor readings simultaneously? I built a mini-version to find out!

This Python system processes real-time data from multiple sensors, intelligently routing information to available processors without overloading any single one. It's like air traffic control for data!

## 🌟 The Challenge I Solved

Imagine 50+ sensors all trying to talk at once to only 5 processors that can handle 2 conversations each. Chaos, right? I built the "traffic cop" that prevents gridlock.

### 🎯 What Makes This Cool
- **Smart Load Balancing**: Automatically finds available processors
- **No Data Collisions**: Uses thread locks to prevent race conditions
- **Efficient Waiting**: Instead of frantic checking, sensors wait patiently
- **Real-time Processing**: Everything happens simultaneously

## 🔧 Under the Hood

```python
# The magic happens here - sensors find their perfect match
def find_home_for_reading(reading, aggregators):
    while not assigned:
        for agg in aggregators:
            if agg.can_take_more():  # "Hey, got room for me?"
                assigned = agg.assign_reading(reading)  # "Jump in!"
