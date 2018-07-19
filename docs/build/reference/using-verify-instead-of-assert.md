---
title: Использование VERIFY вместо ASSERT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- assert
dev_langs:
- C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 712c22bec1d6ce2d67208de9a139dff7621ad4cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376563"
---
# <a name="using-verify-instead-of-assert"></a>Использование VERIFY вместо ASSERT
Предположим, что при запуске отладочной версии приложения MFC, нет никаких проблем. Однако версии того же приложения аварийно завершает работу, возвращает неверные результаты и не функционирует других Аномальное поведение.  
  
 Эта проблема может возникать при размещении важные кода с помощью оператора ASSERT для проверки того, что оно работает правильно. Так как операторы ASSERT закомментированы в сборке выпуска программы MFC, код не выполняется в сборке выпуска.  
  
 Если вы используете ASSERT на подтверждение вызов функции, рассмотрите возможность использования [ПРОВЕРЬТЕ](../../mfc/reference/diagnostic-services.md#verify) вместо него. Макрос VERIFY оценивает собственные аргументы в обоих отладки и выпуска сборок приложения.  
  
 Другой рекомендуется назначить возвращаемое значение функции во временную переменную и затем проверить переменную в операторе ASSERT.  
  
 Рассмотрим следующий фрагмент кода:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Данный код корректно работает в отладочной версии приложения MFC. Если вызов `calloc( )` завершается ошибкой, отобразится диагностическое сообщение, содержащее имя файла и номер строки. Однако в окончательной сборке приложения MFC:  
  
-   вызов `calloc( )` никогда не выполняется, если оставить `buf` неинициализированным, или  
  
-   `strcpy_s( )` Копирует "`Hello, World`" в произвольный участок памяти, сбой в приложении или вследствие чего система перестает отвечать на запросы, или  
  
-   `free()` пытается освободить память, которая не была выделена.  
  
 Использовать ASSERT правильно, в образце кода необходимо заменить следующее:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Или можно использовать вместо этого ПРОВЕРЬТЕ:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## <a name="see-also"></a>См. также  
 [Устранение проблем сборки выпуска](../../build/reference/fixing-release-build-problems.md)