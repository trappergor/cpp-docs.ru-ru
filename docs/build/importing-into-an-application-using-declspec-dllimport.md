---
title: Импорт в приложение с помощью __declspec(dllimport) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82974ec688fbe688c98188c2e99a54462da81165
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>Импорт в приложение с помощью __declspec(dllimport)
Говорят, что программа, которая использует открытые символы, определенные библиотекой DLL их импортировать. При создании файлов заголовка для приложений, использующих библиотеки DLL для сборки, используйте **__declspec(dllimport)** для объявления открытых символов. Ключевое слово **__declspec(dllimport)** работает ли экспортировать DEF-файлы или с **__declspec(dllexport)** ключевое слово.  
  
 Чтобы сделать код более удобочитаемым, определить макрос для **__declspec(dllimport)** , а затем использовать макрос для объявления каждого импортируемого символа:  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 С помощью **__declspec(dllimport)** является необязательным при объявлении функций, хотя компилятор выдает более эффективный код, при использовании ключевого слова. Тем не менее, необходимо использовать **__declspec(dllimport)** исполняемый файл для доступа к открытым символам и объектам библиотеки DLL. Обратите внимание, что пользователям библиотеки DLL также необходимо связаться с библиотекой импорта.  
  
 Можно использовать один и тот же файл заголовка для клиентского приложения и библиотеки DLL. Чтобы сделать это, используйте специальный символ препроцессора, означает ли это построение библиотеки DLL или клиентское приложение. Пример:  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Импорт и экспорт встроенных функций](../build/importing-and-exporting-inline-functions.md)  
  
-   [Взаимный импорт](../build/mutual-imports.md)  
  
## <a name="see-also"></a>См. также  
 [Импорт в приложение](../build/importing-into-an-application.md)