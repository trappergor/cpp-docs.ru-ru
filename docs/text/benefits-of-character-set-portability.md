---
title: Преимущества переносимости кодировки
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 446d59fe62999e5be652be5efabb53fd907fcd88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631355"
---
# <a name="benefits-of-character-set-portability"></a>Преимущества переносимости кодировки

Можно обеспечить с помощью функций переносимость среды выполнения MFC и C, даже если вы не собираетесь сейчас интернационализировать приложение:

- Разработка переносимых приложений делает базу кода гибкие. Вы можете позже его легко для Юникода и MBCS.

- Использование Юникода повышает эффективность своих приложений для Windows. Поскольку в Windows используется Юникод, строки не в Юникоде, передавалась и от операционной системы должны быть переведены, что снижает производительность.

## <a name="see-also"></a>См. также

[Юникод и многобайтовая кодировка](../text/unicode-and-mbcs.md)<br/>
[Поддержка Юникода](../text/support-for-unicode.md)