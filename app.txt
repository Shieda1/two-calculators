// https://www.omnicalculator.com/conversion/mg-to-ml

const v =  document.getElementById('v');
const btn = document.getElementById('btn');
const result = document.getElementById('result');

// radio buttons
const mgRadio = document.getElementById('mgRadio');
const mlRadio = document.getElementById('mlRadio');

let mg;
let ml = v; 

// labels of the inpust
const variable = document.getElementById('variable');

mgRadio.addEventListener('click', function() {
  variable.textContent = 'ml';
  ml = v;
  result.textContent = '';
});

mlRadio.addEventListener('click', function() {
  variable.textContent = 'mg';
  mg = v;
  result.textContent = '';
});

btn.addEventListener('click', function() {
  
  if(mgRadio.checked)
    result.textContent = `mg = ${computemg().toFixed(5)}`;

  else if(mlRadio.checked)
    result.textContent = `ml = ${computeml().toFixed(5)}`;
})

// calculation

function computemg() {
  return Number(ml.value) * 1000;
}

function computeml() {
  return Number(mg.value) / 1000;
}