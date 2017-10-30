# polyglot-service
A micro service for small natural language processing, powered by Polyglot.

# About Polyglot
- https://github.com/aboSamoor/polyglot
- http://polyglot.readthedocs.io/

# Launch example

    #!/bin/sh

    docker run --rm -d -p 34567:80 turbulent/polyglot-service

# Services Available
## Detect Language
After launching, try these requests:

    #!/bin/sh

    wget -q -O - "http://localhost:34567/detect?q=Hello World!"
    wget -q -O - "http://localhost:34567/detect?q=Ceci n'est pas un pipe"
    wget -q -O - "http://localhost:34567/detect?q=我需要你的帮助。这是紧急情况。"
    wget -q -O - "http://localhost:34567/detect?q=我需要你的幫助。這是緊急情況。"
    wget -q -O - "http://localhost:34567/detect?q=Все люди рождаются свободными и равными в своем достоинстве и правах."
    wget -q -O - "http://localhost:34567/detect?q=Всі люди народжуються вільними і рівними у своїй гідності та правах."

### Detect Language Responses
The responses will be JSON, featuring HTML-oriented "locale", confidence level,
and the count of "read_bytes":

    {"locale":"en", "confidence":"92.0", "read_bytes": "1194"}
    {"locale":"fr", "confidence":"95.0", "read_bytes": "890"}
    {"locale":"zh", "confidence":"97.0", "read_bytes": "2048"}
    {"locale":"zh-Hant", "confidence":"97.0", "read_bytes": "1923"}
    {"locale":"ru", "confidence":"99.0", "read_bytes": "927"}
    {"locale":"uk", "confidence":"99.0", "read_bytes": "851"}

# Copyright & License
Copyright (C) 2017  Turbulent Media inc.

GPLv3 - See LICENSE file
