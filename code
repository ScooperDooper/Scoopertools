
function doGet() {
  // This creates and serves the HTML from the file named 'Index'
  return HtmlService.createTemplateFromFile('Index').evaluate();
}

function splitQueries(concatenatedString) {
  // Your existing splitQueries function logic
  var queries = concatenatedString.split(" OR ");
  var output = [];
  var currentBlock = "";

  queries.forEach(function(query, index) {
    // Append " OR " if it's not the last query
    var appendOr = index < queries.length - 1 ? " OR " : "";
    var tempBlock = currentBlock + query + appendOr;

    if (tempBlock.length > 4096) {
      // Push the current block to output and start a new block with the current query
      output.push(currentBlock);
      currentBlock = query + appendOr;
    } else {
      // Add the query to the current block
      currentBlock = tempBlock;
    }
  });

  // Add the last block if it's not empty
  if (currentBlock.trim() !== "") {
    output.push(currentBlock);
  }
  
  return output;
}

function includeOR() {
  return HtmlService.createTemplateFromFile('OR').evaluate();
}

function include(filename) {
    return HtmlService.createHtmlOutputFromFile(filename).getContent();
}

// Ensure there's a function to serve inspiretool.html if it's not already there
function getInspireTool() {
    return HtmlService.createHtmlOutputFromFile('inspiretool').getContent();
  
}



