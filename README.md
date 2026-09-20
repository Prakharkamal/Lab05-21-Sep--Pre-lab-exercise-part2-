/*
 * Calculates the final travel cost.
 *
 * Parameters:
 *   distance : Travel distance in kilometres (1-1000).
 *   age      : Passenger's age (1-100).
 *   luggage  : Luggage weight in kilograms (0-50).
 *   weekend  : 1 for a weekend, 0 for a weekday.
 *
 * Apply the following steps IN ORDER:
 *
 * 1. Calculate the base fare:
 *
 *      - Distance up to 50 km:
 *          Rs. 5 per kilometre.
 *
 *      - Distance from 51 to 150 km:
 *          Rs. 250 for the first 50 km,
 *          plus Rs. 4 per kilometre beyond 50 km.
 *          Example: For 52 km, the fare is
 *          250 + (52 - 50) * 4 = Rs. 258.
 *
 *      - Distance above 150 km:
 *          Rs. 650 for the first 150 km,
 *          plus Rs. 3 per kilometre beyond 150 km.
 *          Example: For 152 km, the fare is
 *          650 + (152 - 150) * 3 = Rs. 656.
 *
 * 2. Apply an age discount to the base fare:
 *
 *      - Age below 12:       50% discount.
 *      - Age from 12 to 17:  20% discount.
 *      - Age from 18 to 59:  No discount.
 *      - Age 60 or above:    30% discount.
 *
 *    Use integer arithmetic:
 *      discount = base_fare * discount_percentage / 100
 *      discounted_fare = base_fare - discount
 *
 * 3. Add a luggage charge:
 *
 *      - Up to 10 kg:         No charge.
 *      - From 11 to 20 kg:    Rs. 100.
 *      - From 21 to 30 kg:    Rs. 250.
 *      - Above 30 kg:         Rs. 500.
 *
 * 4. If it is a weekend, add a surcharge based on distance:
 *
 *      - Distance up to 100 km: Rs. 50.
 *      - Distance above 100 km: Rs. 100.
 *
 * 5. If the final cost is below Rs. 100, set it to Rs. 100.
 *
 * 6. Return the final cost.
 *
 * Examples:
 *   calculate_trip_cost(40, 10, 5, 0)   -> 100
 *   calculate_trip_cost(100, 30, 15, 1) -> 600
 *   calculate_trip_cost(200, 65, 25, 1) -> 910
 */
