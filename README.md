# Search Engine Project

## 3. Форматы JSON
- **config.json**
  ```json
  {
    "config": {
      "name": "SkillboxSearchEngine",
      "version": "0.1",
      "max_responses": 5
    },
    "files": [
      "resources/file001.txt",
      "resources/file002.txt",
      "resources/file003.txt"
    ]
  }
  ```
  - `name`: название приложения.
  - `version`: версия конфигурации (должно быть `"0.1"`).
  - `max_responses`: максимальное число результатов на запрос.
  - `files`: массив путей к текстовым файлам.

- **requests.json**
  ```json
  {
    "requests": [
      "пример запроса",
      "еще один запрос"
    ]
  }
  ```
  - `requests`: массив строковых запросов.

- **answers.json**
  ```json
  {
    "answers": {
      "request001": {
        "result": "true",
        "relevance": [
          { "docid": 7, "rank": 1.0 },
          { "docid": 14, "rank": 1.0 },
          { "docid": 2, "rank": 0.566667 }
        ]
      },
      "request002": {
        "result": "false"
      }
    }
  }
  ```

  ## 5. Сборка и запуск
```bash
mkdir build && cd build
cmake ..            # Генерация сборочных файлов
cmake --build .     # Сборка библиотеки, исполняемого файла и тестов
```

Запуск поисковой программы:
```bash
./search_engine    # создаст answers.json в текущей папке
```

Запуск тестов GoogleTest:
```bash
ctest              # выполняет все тесты и показывает результаты
```

