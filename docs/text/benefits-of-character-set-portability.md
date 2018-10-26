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
ms.openlocfilehash: d016b95ea2a2d5d94b8db47a2d6c9d5cc577083f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064450"
---
# <a name="benefits-of-character-set-portability"></a>Преимущества переносимости кодировки

Можно обеспечить с помощью функций переносимость среды выполнения MFC и C, даже если вы не собираетесь сейчас интернационализировать приложение:

- Разработка переносимых приложений делает базу кода гибкие. Вы можете позже его легко для Юникода и MBCS.

- Использование Юникода повышает эффективность своих приложений для Windows. Поскольку в Windows используется Юникод, строки не в Юникоде, передавалась и от операционной системы должны быть переведены, что снижает производительность.

## <a name="see-also"></a>См. также

[Юникод и многобайтовая кодировка](../text/unicode-and-mbcs.md)<br/>
[Поддержка Юникода](../text/support-for-unicode.md)