---
title: Импорт в приложение с помощью __declspec(dllimport)
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: 50b630334cfd8752935b54549190d698fa5136bb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223984"
---
# <a name="import-into-an-application-using-__declspecdllimport"></a>Импорт в приложение с помощью __declspec(dllimport)

Программа, использующая открытые символы, определенные библиотекой DLL, импортирует их. При создании файлов заголовков для приложений, использующих библиотеки DLL для сборки, используйте **`__declspec(dllimport)`** в объявлениях открытых символов. Ключевое слово **`__declspec(dllimport)`** действует независимо от того, выполняете ли вы экспорт с файлами DEF или с помощью ключевого слова **`__declspec(dllexport)`** .

Чтобы сделать код более удобочитаемым, определите макрос для **`__declspec(dllimport)`** , а затем используйте макрос для объявления каждого импортированного символа:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

Использовать **`__declspec(dllimport)`** в объявлениях функций необязательно, но при применении этого ключевого слова компилятор создает более эффективный код. Однако необходимо использовать **`__declspec(dllimport)`** для импорта исполняемого файла, чтобы получить доступ к открытым символам и объектам данных библиотеки DLL. Обратите внимание, что пользователям библиотеки DLL по-прежнему необходимо связываться с библиотекой импорта.

Вы можете использовать один и тот же файл заголовка для библиотеки DLL и для клиентского приложения. Для этого используйте специальный символ препроцессора, который указывает, выполняется сборка библиотеки DLL или сборка клиентского приложения. Пример:

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
