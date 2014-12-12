#!/usr/bin/ruby
def det(arr)  #YES,in the dirty recursive way!!
  arr.length.times do |i|
    arr[0].length.times do |j|
      arr[i][j] = Float(arr[i][j])
    end
  end
  if arr[0].length == 1
    return 0
  elsif arr[0].length == 2
    return (arr[0][0]*arr[1][1] - arr[0][1]*arr[1][0])
  else
    d = 0
    temp = Array.new(arr[0].length-1){Array.new(arr[0].length-1)}
    arr[0].length.times do |p|
      h = 0
      k = 0
      arr[0].length.times do |i|
        arr[0].length.times do |j|
          if (i==0||j==p)
            next
          end
          temp[h][k] = arr[i][j]
          k += 1
          if (k==arr[0].length-1)
            h += 1
            k=0
          end
        end
      end
      d += arr[0][p]*((-1)**p)*det(temp)
    end
    return d
  end
end
def matrixRp(arr1,arr2,lineNum)
  result = Array[]
  arr1.each{|row|
    result.push(row.clone)
  }
  result.length.times do |i|
    result[i][lineNum] = arr2[i]
  end
  return result
end
ifInitLine = FALSE
matrixProperty = Array.new
matrixContent = Array.new
matrixContent2 = Array.new
File.open('input.txt', 'r') do |f1|
  while line = f1.gets
    lineArr = line.split(" ")
    if !ifInitLine
      matrixProperty = lineArr
      ifInitLine = TRUE
    else
      matrixContent2.push(lineArr.pop())
      matrixContent.push(lineArr)
    end
  end
end
matrixContent.length.times do |i|
  puts format("%.2f",(Float(det(matrixRp(matrixContent,matrixContent2,i))) / Float(det(matrixContent))))
end

#BTW,you should banned R as matlab
