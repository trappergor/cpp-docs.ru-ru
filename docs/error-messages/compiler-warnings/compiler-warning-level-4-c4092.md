---
title: Предупреждение компилятора (уровень 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: 6786d692785dbca575d4b241b7b3e3d40575b686
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198553"
---
# <a name="compiler-warning-level-4-c4092"></a>Предупреждение компилятора (уровень 4) C4092

sizeof возвращает "unsigned long"

Операнд оператора `sizeof` был очень большим, поэтому `sizeof` возвращал неподписанный **Long**. Это предупреждение появляется в разделе расширения Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). В режиме совместимости с ANSI (/ZA) результат усекается.
