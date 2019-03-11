---
title: Преимущества переносимости кодировки
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 0ca7e46cabb2d98a64a244863f8574a3e9e2a456
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750010"
---
# <a name="benefits-of-character-set-portability"></a>Преимущества переносимости кодировки

Можно обеспечить с помощью функций переносимость среды выполнения MFC и C, даже если вы не собираетесь сейчас интернационализировать приложение:

- Разработка переносимых приложений делает базу кода гибкие. Вы можете позже его легко для Юникода и MBCS.

- Использование Юникода повышает эффективность своих приложений для Windows. Поскольку в Windows используется Юникод, строки не в Юникоде, передавалась и от операционной системы должны быть переведены, что снижает производительность.

## <a name="see-also"></a>См. также

[Юникод и многобайтовая кодировка](../text/unicode-and-mbcs.md)<br/>
[Поддержка Юникода](../text/support-for-unicode.md)
