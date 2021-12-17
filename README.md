# matlab
function output = blur(img, w)
[row, col] = size(img);
output = img;
n = floor((2*w + 1)/2);
for i = 1:row
for j = 1:col
left = j - n;
right = j + n;
top = i - n;
bottom = i + n;
if left < 1
left = 1;
end
if top < 1
top = 1;
end
if right > col
right = col;
end
if bottom > row
bottom = row;
end
mat = img(top:bottom, left:right);
output(i, j) = mean(mean(mat));
end
end
end
