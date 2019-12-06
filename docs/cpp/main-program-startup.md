---
title: 'Функция main: запуск программы'
ms.date: 11/04/2016
f1_keywords:
- vc.main.startup
- _tmain
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
ms.openlocfilehash: 29e1b77c2e36c66e4e6fc4ec30a73af4d57654a0
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857441"
---
# <a name="main-program-startup"></a>Функция main: запуск программы

Специальная функция с именем **Main** — это начальная точка выполнения для всех C и C++ программ. При написании кода, который соответствует модели программирования Юникода, можно использовать `wmain`, который является версией **Main**для расширенных символов.

Функция **Main** не предопределена компилятором. Она должна присутствовать в тексте программы.

Синтаксис объявления для **Main** — это

```cpp
int main();
```

или, если требуется,

```cpp
int main(int argc, char *argv[], char *envp[]);
```

**Блок, относящийся только к системам Майкрософт**

Синтаксис объявления функции `wmain` выглядит следующим образом:

```cpp
int wmain( );
```

или, если требуется,

```cpp
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

Можно также использовать `_tmain`, который определен в файле Tchar. h. `_tmain` разрешается в **Main** , если не определено _UNICODE. В противном случае функция `_tmain` разрешается в функцию `wmain`.

Кроме того, функции **Main** и `wmain` могут быть объявлены как возвращающая значение **void** (без возвращаемого значения). Если вы объявили **Main** или `wmain` как возвращаемое **значение void**, нельзя вернуть код выхода в родительский процесс или операционную систему с помощью оператора [return](../cpp/return-statement-in-program-termination-cpp.md) . Чтобы вернуть код выхода, когда **Main** или `wmain` объявлены как **void**, необходимо использовать функцию [Exit](../cpp/exit-function.md) .

**Завершение блока, относящегося только к системам Майкрософт**

Типы для параметров `argc` и `argv` определяются языком. Имена `argc`, `argv` и `envp` являются традиционными, но они не обязательны для компилятора. Дополнительные сведения и пример см. в разделе [определения аргументов](../cpp/argument-definitions.md).

## <a name="see-also"></a>См. также:

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Использование wmain вместо main](../cpp/using-wmain-instead-of-main.md)<br/>
[Ограничения функции main](../cpp/main-function-restrictions.md)<br/>
[Анализ аргументов командной строки C++](../cpp/parsing-cpp-command-line-arguments.md)
