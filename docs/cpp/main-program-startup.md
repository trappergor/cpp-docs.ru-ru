---
title: 'основной: Запуск программы'
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
ms.openlocfilehash: 358ae8ec88281bab741393b1196ee2a1e615e896
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345042"
---
# <a name="main-program-startup"></a>основной: Запуск программы

Это специальная функция с именем **основной** является начальной точкой выполнения для всех программ C и C++. Написание кода, который соответствует модели программирования Юникода можно использовать `wmain`, которая является версией Юникода **основной**.

**Основной** функция не является стандартным компилятором. Она должна присутствовать в тексте программы.

Синтаксис объявления **основной** —

```cpp
int main();
```

или, если требуется,

```cpp
int main(int argc, char *argv[], char *envp[]);
```

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Синтаксис объявления функции `wmain` выглядит следующим образом:

```cpp
int wmain( );
```

или, если требуется,

```cpp
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

Можно также использовать `_tmain`, который определен в файле tchar.h. `_tmain` разрешается **основной** Если определяется _UNICODE. В противном случае функция `_tmain` разрешается в функцию `wmain`.

Кроме того **основной** и `wmain` функции могут быть объявлены как возвращающий **void** (без возвращаемого значения). При объявлении **основной** или `wmain` как возвращающий **void**, код выхода не может вернуться к родительскому процессу или операционной системы с помощью [возвращают](../cpp/return-statement-in-program-termination-cpp.md) инструкции. Для возврата кода завершения, когда **основной** или `wmain` объявляется как **void**, необходимо использовать [выйти из](../cpp/exit-function.md) функции.

**Завершение блока, относящегося только к системам Майкрософт**

Типы для параметров `argc` и `argv` определяются языком. Имена `argc`, `argv` и `envp` являются традиционными, но они не обязательны для компилятора. Дополнительные сведения и пример см. в разделе [определения аргументов](../cpp/argument-definitions.md).

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Использование wmain вместо main](../cpp/using-wmain-instead-of-main.md)<br/>
[Ограничения функции main](../cpp/main-function-restrictions.md)<br/>
[Анализ аргументов командной строки C++](../cpp/parsing-cpp-command-line-arguments.md)
