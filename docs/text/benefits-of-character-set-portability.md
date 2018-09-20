---
title: Преимущества переносимости кодировки | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 115a4524f3b11d847291015f3bee5ca10f628310
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423446"
---
# <a name="benefits-of-character-set-portability"></a>Преимущества переносимости кодировки

Можно обеспечить с помощью функций переносимость среды выполнения MFC и C, даже если вы не собираетесь сейчас интернационализировать приложение:

- Разработка переносимых приложений делает базу кода гибкие. Вы можете позже его легко для Юникода и MBCS.

- Использование Юникода повышает эффективность своих приложений для Windows. Поскольку в Windows используется Юникод, строки не в Юникоде, передавалась и от операционной системы должны быть переведены, что снижает производительность.


## <a name="see-also"></a>См. также

[Юникод и многобайтовая кодировка](../text/unicode-and-mbcs.md)<br/>
[Поддержка Юникода](../text/support-for-unicode.md)