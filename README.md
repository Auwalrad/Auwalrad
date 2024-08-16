clear;clc;close all
I= imread("spln increase gain.JPG");
% I= imread("AVI.AVI");
imshow(I)
roi = drawrectangle('LineWidth',1,'Color','red');

croppedImage = imcrop(I, roi.Position); 
meanValue = mean2(croppedImage)
SDValue = std2(croppedImage)% Get values in the rectangle and averaged.

% nStr = num2str(meanValue)
hold on

text(350,180,['Mean = ',num2str(meanValue)])
text(350,200,['SD = ',num2str(SDValue)])
