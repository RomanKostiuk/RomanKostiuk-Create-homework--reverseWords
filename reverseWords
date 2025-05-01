const fs = require('fs');
const path = require('path');

function reverseWords(text) {
    return text.split(/(\s+)/)
               .map(word => word.split('').reverse().join(''))
               .join('');
}

function processFile(inputFile, outputFile) {
    fs.readFile(inputFile, 'utf8', (err, data) => {
        if (err) {
            console.error('Не вдалося прочитати файл:', err);
            return;
        }

        const reversedText = reverseWords(data);

        fs.writeFile(outputFile, reversedText, 'utf8', err => {
            if (err) {
                console.error('Не вдалося записати у файл:', err);
                return;
            }
            console.log(`Файл успішно створено за адресою ${outputFile}`);
        });
    });
}

const inputFilePath = path.join(__dirname, 'input.txt');
const outputFilePath = path.join(__dirname, 'output.txt');

processFile(inputFilePath, outputFilePath);
