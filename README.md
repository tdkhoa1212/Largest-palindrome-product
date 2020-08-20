import time
def largestPalindromeProduct(digits):
  min, max, temp, pal = '1', '', 0, 0
  for _ in range (1,digits):
    min += '0'
  for _ in range (0,digits):
    max += '9'
  min = int(min)-1
  max = int(max)
  start = time.time()
  for num1 in range (max,min,-1):
    for num2 in range (num1,min,-1):
      temp = num1 * num2
      if temp < pal:
        break
      if str(temp) == "".join(reversed(str(temp))):
        pal = temp
  end = time.time()
  print(pal, end=' ')
  print(end-start)
largestPalindromeProduct(3)
