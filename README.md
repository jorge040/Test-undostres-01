# Test-undostres-01
write a function that solves the following exercise


Hola use el lenguaje de phython para hacer los ejercisios:

def swap(nums, i, j):
	temp = nums[i]
	nums[i] = nums[j]
	nums[j] = temp

def partition(nums):
	pIndex = 0

	for i in range(len(nums)):
		if nums[i] > 0:		# pivot is 0:
			swap(nums, i, pIndex)
			pIndex += 1

	return pIndex

def findSmallestMissing(nums):

	k = partition(nums)

	for i in range(k):

		val = abs(nums[i])

		if val-1 < k and nums[val-1] >= 0:
			nums[val-1] = -nums[val-1]

	for i in range(k):
		if nums[i] > 0:
			return i + 1

	return k + 1

if __name__ == '__main__':

	nums = [1, 2, 0]

	print('The smallest positive missing number is', findSmallestMissing(nums))
  
  ![image](https://user-images.githubusercontent.com/46494068/191123618-ac9787fa-d77a-40fc-bb89-cde237831c53.png)
