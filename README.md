# Data-structure-python-program-1
def subarraySum(arr, target):
    start = 0
    curr_sum = 0

    for end in range(len(arr)):
        curr_sum += arr[end]

        while curr_sum > target and start <= end:
            curr_sum -= arr[start]
            start += 1

        if curr_sum == target:
            return [start + 1, end + 1]

    return [-1]


# Example
arr = [1, 2, 3, 7, 5]
target = 12
print(subarraySum(arr, target))
