---
title: "Общие сведения о LIB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef3d1e57371fdea62bb557830baca633f4165637
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-lib"></a>Общие сведения о LIB
LIB создает стандартные библиотеки, библиотеки импорта и экспорта файлов можно использовать с [ССЫЛКУ](../../build/reference/linker-options.md) при сборке программы. LIB запускается из командной строки.  
  
 LIB можно использовать в следующих режимах:  
  
-   [Создание или изменение библиотеки COFF](../../build/reference/managing-a-library.md)  
  
-   [Извлечение элемента-объекта в файл](../../build/reference/extracting-a-library-member.md)  
  
-   [Создание файла экспорта и библиотеки импорта](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 Эти режимы являются взаимоисключающими; LIB можно использовать в режиме только один одновременно.  
  
## <a name="lib-options"></a>Параметры LIB  
 В следующей таблице перечислены параметры lib.exe со ссылками на дополнительные сведения.  
  
 **/ DEF**  
 Создание библиотеки импорта и файла экспорта.  
  
 Дополнительные сведения см. [построение библиотеки импорта и экспорта файла](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ ERRORREPORT**  
 Отправьте в Майкрософт сведения о внутренних ошибках lib.exe.  
  
 Дополнительные сведения см. [запуск LIB](../../build/reference/running-lib.md).  
  
 **И ЭКСПОРТА**  
 Экспортирует функцию из программы.  
  
 Дополнительные сведения см. [построение библиотеки импорта и экспорта файла](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ EXTRACT**  
 Создайте Объектный OBJ-файл, содержащий копию элемента существующей библиотеки.  
  
 Дополнительные сведения см. [извлечение члена библиотеки](../../build/reference/extracting-a-library-member.md).  
  
 **/ INCLUDE**  
 Добавляет символ в таблицу символов.  
  
 Дополнительные сведения см. [построение библиотеки импорта и экспорта файла](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ LIBPATH**  
 Переопределяет путь к библиотеке среды.  
  
 Дополнительные сведения см. [Управление библиотекой](../../build/reference/managing-a-library.md).  
  
 **/ LIST**  
 Отображает сведения о выходной библиотеке в стандартный вывод.  
  
 Дополнительные сведения см. [Управление библиотекой](../../build/reference/managing-a-library.md).  
  
 **/ ПАРАМЕТР LTCG**  
 В результате библиотеки для сборки с помощью создания кода во время компоновки.  
  
 Дополнительные сведения см. [запуск LIB](../../build/reference/running-lib.md).  
  
 **/ MACHINE**  
 Указывает целевую платформу программы.  
  
 Дополнительные сведения см. [запуск LIB](../../build/reference/running-lib.md).  
  
 **В ИМЯ**  
 При сборке библиотеки импорта задает имя библиотеки DLL, для которых создается библиотека импорта.  
  
 Дополнительные сведения см. [Управление библиотекой](../../build/reference/managing-a-library.md).  
  
 **/ ПАРАМЕТР NODEFAULTLIB**  
 Удаляет один или несколько стандартных библиотек из списка библиотек, в которых осуществляется поиск при разрешении внешних ссылок.  
  
 Дополнительные сведения см. [Управление библиотекой](../../build/reference/managing-a-library.md).  
  
 **/ NOLOGO**  
 Подавление отображения LIB об авторских правах и номере версии и предотвращает отображение команд командного файла.  
  
 Дополнительные сведения см. [запуск LIB](../../build/reference/running-lib.md).  
  
 **/ OUT**  
 Переопределяет имя выходного файла по умолчанию.  
  
 Дополнительные сведения см. [Управление библиотекой](../../build/reference/managing-a-library.md).  
  
 **И УДАЛЕНИЕ**  
 Пропуск объекта из выходной библиотеки.  
  
 Дополнительные сведения см. [Управление библиотекой](../../build/reference/managing-a-library.md).  
  
 **/ SUBSYSTEM**  
 Указывает операционной системе, как запустить программу, созданную путем связывания с выходной библиотеки.  
  
 Дополнительные сведения см. [Управление библиотекой](../../build/reference/managing-a-library.md).  
  
 **/ VERBOSE**  
 Отображает подробные сведения о ходе выполнения сеанса, включая имена добавляемых OBJ-файлов.  
  
 Дополнительные сведения см. [запуск LIB](../../build/reference/running-lib.md).  
  
 **/ WX**  
 Обрабатывать предупреждения как ошибки.  
  
 Дополнительные сведения см. [запуск LIB](../../build/reference/running-lib.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по LIB](../../build/reference/lib-reference.md)   
 [Входные LIB-файлы](../../build/reference/lib-input-files.md)   
 [Выходные LIB-файлы](../../build/reference/lib-output-files.md)   
 [Прочие выходные данные LIB](../../build/reference/other-lib-output.md)   
 [Структура библиотеки](../../build/reference/structure-of-a-library.md)