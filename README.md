# Современные правила написания кода на Python

Современные правила написания кода на Python основаны на PEP 8 (Python Enhancement Proposal 8) — официальном руководстве по стилю кода. Вот основные рекомендации:

Отступы и пробелы

Отступы: 4 пробела на уровень (не табуляция).
Пробелы вокруг операторов:

x = 5  # правильно
y = x + 10

Нет пробелов внутри скобок и перед запятыми:

list_example = [1, 2, 3]  # правильно

Длина строки
Максимум 79 символов для кода (по PEP 8).
Для комментариев и docstrings — 72 символа.
Перенос строк через \ или скобки:

long_string = (
    "Это очень длинная строка, "
    "которую нужно перенести."
)

Именование
Переменные и функции: snake_case (user_name, calculate_total).

Константы: UPPER_CASE (MAX_USERS, DEFAULT_VALUE).


Импорты
Группировать импорты в порядке:
Стандартные библиотеки (import os).
Сторонние библиотеки (import numpy).
Локальные модули (from . import utils).

Каждый импорт — на новой строке:

import os
import sys
from typing import List, Dict


Пустые строки
2 пустые строки перед объявлением класса или функции верхнего уровня.
1 пустая строка между методами класса.
Внутри функции — для логического разделения блоков.

Пример хорошо оформленного кода

import os
from typing import List


class UserManager:
    """Управляет пользователями в системе."""

    def __init__(self, max_users: int) -> None:
        self._max_users = max_users
        self._users: List[str] = []

    def add_user(self, username: str) -> bool:
        """Добавляет пользователя, если есть место."""
        if len(self._users) < self._max_users:
            self._users.append(username)
            return True
        return False


def main() -> None:
    manager = UserManager(10)
    manager.add_user("alice")


if __name__ == "__main__":
    main()

Соблюдение этих правил делает код читаемым, единообразным и удобным для поддержки. Для автоматизации используйте инструменты вроде pre-commit hooks с black и flake8.
