---
title: Описание аргумента | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- envp argument
- main function, syntax
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b8508b5a14e67092339a456f5b85f78d17906a5
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082544"
---
# <a name="argument-description"></a>Описание аргумента

Параметр `argc` в функциях **main** и **wmain** выражается целым числом и обозначает количество аргументов, переданных в программу из командной строки. Поскольку имя программы считается аргументом, значение `argc` по крайней мере равно единице.

## <a name="remarks"></a>Примечания

Параметр `argv` является массивом указателей на строки, завершающиеся значением NULL, который представляет аргументы программы. Каждый элемент массива указывает на строковое представление аргумента, переданного в **main** (или **wmain**). (Дополнительные сведения о массивах см. в разделе [Объявления массивов](../c-language/array-declarations.md).) Параметр `argv` можно объявить как массив указателей на тип `char` (`char *argv[]`) или как указатель на указатели на тип `char` (`char **argv`). Параметр `argv` в **wmain** можно объявить как массив указателей на тип `wchar_t` (`wchar_t *argv[]`) или как указатель на указатели на тип `wchar_t` (`wchar_t **argv`).

По соглашению параметр `argv`**[0]** содержит команду, которая использовалась для вызова программы.  Однако процесс можно инициализировать с помощью [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa), а если указаны и первый, и второй аргументы (`lpApplicationName` и `lpCommandLine`), то `argv`**[0]** не будет содержать имени исполняемого файла. Чтобы гарантированно получить имя исполняемого файла, используйте [GetModuleFileName](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea).

Последний указатель (`argv[argc]`) имеет значение **NULL**. (Альтернативный метод получения сведений о переменной среды см. в разделе [getenv](../c-runtime-library/reference/getenv-wgetenv.md) *Справочника по библиотеке времени выполнения*.)

**Блок, относящийся только к системам Microsoft**

Параметр `envp` является указателем на массив строк, завершающихся значением NULL, которые представляют значения, заданные в переменных среды пользователя. Параметр `envp` можно объявить как массив указателей на тип `char` (`char *envp[]`) или как указатель на указатели на тип `char` (`char **envp`). Параметр `envp` в функции **wmain** можно объявить как массив указателей на `wchar_t` (`wchar_t *envp[]`) или как указатель на указатели на `wchar_t` (`wchar_t **envp`). Конец массива определяется указателем **NULL** \*. Обратите внимание, что передаваемый в **main** или **wmain** блок окружения является "замороженной" копией текущего окружения. Если окружение будет позднее изменена путем вызова **_putenv** или `_wputenv`, изменится только текущее окружение (которое возвращают `getenv`/`_wgetenv` и переменные `_environ` или `_wenviron`); но не блок, на который указывает `envp`. Параметр `envp` совместим с ANSI в C, но не в C++.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Функция main и выполнение программ](../c-language/main-function-and-program-execution.md)