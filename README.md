# IntegerToRoman
class Solution:
    def intToRoman(self, num: int) -> str:
        romans = { 
            1: 'I',
            4: 'IV',
            5: 'V',
            9: 'IX',
            10: 'X',
            40: 'XL',
            50: 'L',
            90: 'XC',
            100: 'C',
            400: 'CD',
            500: 'D',
            900: 'CM',
            1000: 'M'
        }
        sortedkeys = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]
        result = ""
        while num > 0:
            print(num)
            for key in sortedkeys:
                if num >=key:
                    quotient = num // key
                    result += romans[key] * quotient
                    num = num % key 
        return result
