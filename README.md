# Notes
This is my personal notes take with ![zettelkasten](https://writingcooperative.com/zettelkasten-how-one-german-scholar-was-so-freakishly-productive-997e4e0ca125) technique.

## Support tool
I use ![neuron](https://github.com/srid/neuron) in order to manage connections between notes

---
## Get notes
The easiest way to get notes is through docker:

```bash
git clone https://github.com/fedeizzo/zettelkasten.git
cd zettelkasten
docker run --rm -t -i -p 8080:8080 -v $(pwd):/notes sridca/neuron neuron rib -ws 0.0.0.0:8080
```

Another way involves neuron installation, for further informations read their documentations.
