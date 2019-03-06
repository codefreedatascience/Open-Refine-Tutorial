![DSL Logo](dsl_logo.png) 

[@brock_dsl](https://twitter.com/brock_dsl)

# Open-Refine-Workshop
## Feel free to work through this workshop using the included [CSV file](chocolate.csv), or any messy data set you have

### Opening the Dataset 
1. Start up OpenRefine - ensure you're in **create project** mode
2. Load the desired files into OpenRefine and click **next**
3. You're currently seeing your data in **Preview Mode**. Here, you can make some basic adjustments to your data
4. If the first few rows of your dataset contain descriptive text, ignore them by checking the **ignore first** box and typing the appropriate number in the box. Click **update preview**
5. You can also adjust the format of your data so that it loads correctly, including CSV files, Excel files, JSON files, and many more
> ![photo1](https://user-images.githubusercontent.com/46492847/53642869-bcfeea00-3c00-11e9-8675-fc549597720b.png)
6. Once you're happy with the first few adjustments, give your project a name and click **create project**

### Basic Data Cleanup
1. One thing that sets OpenRefine apart from other data management tools like Excel is the ability to work with large datasets. It does this by loading a maximum of 50 rows of your dataset at a time. Looking at fewer rows allows OpenRefine to work quickly and efficiently, whereas a program like Excel could take forever to load hundreds of thousands of rows of data. Depending on the size of your dataset, you may prefer to look at 50 rows to see as much of your data as possible
> ![photo2](https://user-images.githubusercontent.com/46492847/53642960-ecadf200-3c00-11e9-9809-782a730c0321.png)
2. If you want to remove columns, you can **open the drop-down menu in the column you want to remove -> choose edit column -> remove column**
> ![photo3](https://user-images.githubusercontent.com/46492847/53643004-02bbb280-3c01-11e9-8378-1f878a383dbc.png)
3. If you want to remove multiple columns at once, or change the order of the columns, **open the drop-down menu on the "All" column on the far left**. From there, choose **edit columns -> re-order/remove columns**
4. From there, it's as simple as dragging and dropping columns that you wish to delete from the left side to the right, and dragging and dropping columns in the order you wish
> ![photo4](https://user-images.githubusercontent.com/46492847/53643026-0a7b5700-3c01-11e9-9418-0f8425dd5d20.png)
5. To re-name your columns, **open the drop-down menu in the column you want to rename -> choose edit column -> re-name this column**
6. A common occurrence in public data is leading and trailing whitespace in specific values. OpenRefine will count any whitespace as part of the value, which can be problematic when you have values that would otherwise be identical if not for extra spaces before or after the value. To get rid of this, **open the drop-down menu in the column you want to fix -> edit cells -> common transforms -> trim leading and trailing whitespace**
> ![photo5](https://user-images.githubusercontent.com/46492847/53643068-20891780-3c01-11e9-97fe-b7b039bc929d.png)

### Filtering and Faceting Data
1. Filters are a good way to search for values in your data *if you know what specific value you're looking for*
2. To create a filter for a column, **open the drop-down menu in the column you want to filter -> choose text filter**
3. From here, you can type in whatever value you're interested in analyzing in your dataset
> ![photo6](https://user-images.githubusercontent.com/46492847/53643078-2979e900-3c01-11e9-9e57-dd0ba7d76bec.png)
4. Facets are a similar, but more sophisticated way of selecting which data you want to analyze or work with. Unlike filters, facets summarize all of the values that appear in the column. From there you can select which data you want to view, and also edit the data if you wish.
5. To create a facet, **open the drop-down menu in the column you want to facet -> choose text facet**
> It's worth noting here that there are multiple kinds of facets, including Numeric and Timeline facets
> You can also create customized facets depending on what kind of data you're working with. For now, 
> we'll stick with Text facets, as they are most common
6. Now, our facet is showing us how many total values there are in this column, how many rows contain each value, and the option to sort the values by name or count

> ![photo7](https://user-images.githubusercontent.com/46492847/53643110-41516d00-3c01-11e9-91ac-7ca99b6bcf66.png)
7. Facets are a helpful way to sort data because they can point out inconsistencies and errors in the data. In this example, we can see that we have a value called "italy" with a lowercase "i", and another value called "Italy" with an uppercase "I". There's a good chance that these values are referring to the same thing, and there are two ways to change this so that these values are represented by the same thing.

> ![photo8](https://user-images.githubusercontent.com/46492847/53643138-4f9f8900-3c01-11e9-85be-03be2800ff89.png)
8. Our first option is to **click directly on the value we want to change -> click edit** and then make the necessary changes
> ![photo9](https://user-images.githubusercontent.com/46492847/53643158-59c18780-3c01-11e9-8789-c3c33c056d53.png)
9. If there are a lot of little mistakes like this in our dataset, we can take advantage of OpenRefine's **cluster feature**
10. To create a cluster, **click *cluster* at the top right corner of the facet**. Now we can see all of the values that are similar. Check the boxes next to the values you want to change, then click **Merge Selected and Close**
> ![photo10](https://user-images.githubusercontent.com/46492847/53643172-6514b300-3c01-11e9-9a58-20fed5b07bcd.png)
11. Finally, you can change individual cells to something completely different. In our example dataset, one column has a lot of cells where the value is "X". The original source tells us that the "X" is meant to denote that the value is unknown. To change the "X" value into something that's easier to interpret, **click directly on the cell -> edit** and then type in whatever you want the cells to say. Once you're happy, **click Apply to all Identical Cells**
> ![photo11](https://user-images.githubusercontent.com/46492847/53643192-7231a200-3c01-11e9-898a-6758373f4453.png)

### Split and Concatenate Columns in a Dataset
1. One way we can manipulate columns is to split values. In our example dataset, there is a column called review date that shows the month and year a review took place. Using OpenRefine, we can split this column into **Month** and **Year**. 
2. **Open the drop-down menu in the column you want to split -> select edit column -> split into several columns**.
> ![photo12](https://user-images.githubusercontent.com/46492847/53643209-7c53a080-3c01-11e9-9d96-804a8e579671.png)
3. The default separator is a comma, but if your values are separated by a space or bracket you can enter that here. For this example, we're also going to **split into 2 columns at most** for this example, but this will depend on how many values you have in your column.
4. If you want to keep your original column, be sure to uncheck **Remove this column**. Then click **OK**
> ![photo13](https://user-images.githubusercontent.com/46492847/53643222-870e3580-3c01-11e9-8a6c-37fcf13986d2.png)
5. Another option in OpenRefine is to do the opposite and concatenate strings and/or values from two or more columns together. In this example, we're going to join our Company_Name and Company_Location column.
6. To start, **open the drop-down menu in the column we want to add to -> select edit column -> add column based on this column**

> ![photo14](https://user-images.githubusercontent.com/46492847/53643238-92616100-3c01-11e9-99e5-ecc94580379d.png)
7. To perform this function, we need to write a GREL expression. If you're unfamiliar with GREL expressions, no need to panic! OpenRefine has their own [repository](https://github.com/OpenRefine/OpenRefine/wiki/GREL-Functions) that goes through the basics of writing GREL expressions. You can also write your expressions in Python if you're familiar with the language
8. For now, we'll work through this expression together. In our example, we want to create a string that is the company name, a space, and then the company location in parentheses.
> ![photo15](https://user-images.githubusercontent.com/46492847/53643261-9f7e5000-3c01-11e9-9c59-b5c09226f14b.png)
9. In our expression in the above photo, **value** refers to the value of the current column - in our case, Company_Location. Since we want to refer to another column in our expression (we're using Company_Name in this example), we'll use the term **cells**. From there, we'll write the name of the column we're combining with, then .value.
10. So, the first part of our expression should read **cells.Company_Name.value**
> ![photo16](https://user-images.githubusercontent.com/46492847/53643276-ac02a880-3c01-11e9-8209-2508ada80672.png)
11. Next, we're going to use a plus sign to join the different values together into one long string. In our expression, we'll type **+"("+value+")"** When you're done, your whole string should look like this -> **cells.Company_Name.value+"("+value+")"**
12. You'll notice that as you're typing the expression, the preview at the bottom changes to show you what the resulting value will be. This preview is very helpful when writing GREL expressions, especially if you're not overly familiar with how to do it. Once you're finished writing your expression, **click OK**. Your new column should now appear in your dataset.
> ![photo17](https://user-images.githubusercontent.com/46492847/53643318-c177d280-3c01-11e9-82c1-f6440a6cbdbd.png)

### Restructuring the Dataset
1. If you're new to OpenRefine, there's no doubt that you'll make mistakes or want to go back a few steps. Fortunately, it's easy to do with OpenRefine's undo/redo feature. To access it, **click the undo/redo tab above where the facets and filters usually appear**

> ![photo18](https://user-images.githubusercontent.com/46492847/53643340-cccafe00-3c01-11e9-9c82-abcd7d5aae9d.png)
2. In this tab, you can see all of the steps you've taken that outline what you've done to your dataset. To go back to a previous version, just click on the last step you were happy with.
3. If you click back to previous steps, everything after those steps will be greyed out. You can still go forward to the greyed out steps, but be aware that if you go back a previous step and the start making new changes and transformations, all of the subsequent steps will be erased permanently.


