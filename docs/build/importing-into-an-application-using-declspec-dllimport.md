---
title: Импорт в приложение с помощью объявления __declspec(dllimport)
ms.date: 11/04/2016
f1_keywords:
- __declspec
- dllimport
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: 30e0f6517f2d749962c5cf49dddb1662c9ccf129
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341647"
---
# <a name="import-into-an-application-using-declspecdllimport"></a>Импорт в приложение с помощью объявления __declspec(dllimport)

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

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также

[Импорт в приложение](importing-into-an-application.md)
