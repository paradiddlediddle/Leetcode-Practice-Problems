public void containerWithTheMostWater () {
        int [] height = {1,8,6,2,5,4,8,25,7};
        
        int maxWaterArea = Integer.MIN_VALUE;
        int leftWallPointer = 0;
        int rightWallPointer = height.length-1;

        while (leftWallPointer < rightWallPointer) {

            int lowerWall = Math.min(height[leftWallPointer], height[rightWallPointer]); // height
            int distanceBetweenWalls = (rightWallPointer - leftWallPointer); // width
            int currentMax = lowerWall * distanceBetweenWalls; // area = wall height x spacesInBetween// storing the lowest wall and its area in hashMap
            maxWaterArea = Math.max(currentMax, maxWaterArea); // updating the max area obtained so far

            //The index with the lowest wall is moved towards the centre.
            if (height[leftWallPointer] < height[rightWallPointer]){ leftWallPointer++; }
            else rightWallPointer--;
        }
