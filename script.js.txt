const data = [
  { name: "Ramesh", id: "101", details: "Village A - Pali" },
  { name: "Suresh", id: "102", details: "Village B - Pali" },
  { name: "Mahesh", id: "103", details: "Village C - Pali" }
];

function searchData() {
  let input = document.getElementById("searchBox").value.toLowerCase();
  let resultDiv = document.getElementById("result");

  let found = data.filter(item =>
    item.name.toLowerCase().includes(input) ||
    item.id.includes(input)
  );

  if (found.length > 0) {
    resultDiv.innerHTML = found.map(item =>
      `<p><b>${item.name}</b> (ID: ${item.id}) - ${item.details}</p>`
    ).join("");
  } else {
    resultDiv.innerHTML = "No record found";
  }
}