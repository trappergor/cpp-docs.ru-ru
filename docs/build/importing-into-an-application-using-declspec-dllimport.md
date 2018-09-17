---
title: Импорт в приложение с помощью объявления __declspec(dllimport) | Документация Майкрософт
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
ms.openlocfilehash: 08a406c8884cdcb9d4b2ead2e61d416ac580fd73
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704090"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>Импорт в приложение с помощью __declspec(dllimport)

Считается, что программа, которая использует открытые символы, определенные библиотекой DLL, импортировать их. При создании файлов заголовков для приложений, использующих библиотеки DLL для сборки с помощью, используйте **__declspec(dllimport)** для объявления открытых символов. Ключевое слово **__declspec(dllimport)** работает ли экспорт с помощью DEF-файлы или **__declspec(dllexport)** ключевое слово.

Чтобы сделать код более удобочитаемым, задайте макрос для **__declspec(dllimport)** , а затем использовать макрос для объявления каждого импортируемого символа:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

С помощью **__declspec(dllimport)** является необязательным при объявлении функций, но компилятор создает более эффективный код, при использовании этого ключевого слова. Тем не менее, необходимо использовать **__declspec(dllimport)** исполняемый файл для доступа к открытым символам и объектам библиотеки DLL. Обратите внимание на то, что пользователи из вашей библиотеки DLL, все равно необходимо связать с библиотекой импорта.

Можно использовать один и тот же файл заголовка для библиотеки DLL и клиентское приложение. Чтобы сделать это, используйте специальный символ препроцессора, указывает ли при построении библиотеки DLL или клиентское приложение. Пример:

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

- [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Импорт и экспорт встраиваемых функций](../build/importing-and-exporting-inline-functions.md)

- [Взаимный импорт](../build/mutual-imports.md)

## <a name="see-also"></a>См. также

[Импорт в приложение](../build/importing-into-an-application.md)