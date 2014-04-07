How to use these visualizations locally:

1. Place the visualization folder in the same folder as your coloring, facility,
   tsp, and vrp folders. (If you want to organize differently see #6 below)
2. In each solver.py that you want to use:
    * At the top, add "import json" near the other import statements
    * At the end of the solve_it function, immediately before the return statement,
      add the following lines:
    
    with open('visdata.js','w') as vis:
        vis.write('var problem_data = ' + json.dumps(input_data) + ';\n')
        vis.write('var solution_data = ' + json.dumps(output_data) + ';')
        
    * exception: in the VRP solver.py file, the output_data variable is named differently:
    
    with open('visdata.js','w') as vis:
        vis.write('var problem_data = ' + json.dumps(input_data) + ';\n')
        vis.write('var solution_data = ' + json.dumps(outputData) + ';')
        
3. Run solver.py for a particular problem. Then in a browser window, open the index.html 
    file in the corresponding visualization folder. Your solution should appear
    automatically.
    
4. If you do another run and want to visualize it, just reload the browser window. 
    
5. The drag-and-drop interface still works as before if you want to look at a different
     solution. 
     
6. If you want a different directory structure, just modify line 13 or 14 in each
     index.html file to point to the visdata.js file in the right folder.