---
title: Неустранимая ошибка C1383
ms.date: 11/04/2016
f1_keywords:
- C1383
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
ms.openlocfilehash: 6c0be830cb56b760f1397ea2b2f81b42a87e9ba6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203090"
---
# <a name="fatal-error-c1383"></a>Неустранимая ошибка C1383

Параметр компилятора /GL несовместим с установленной версией среды CRL

Ошибка C1383 происходит, когда вы используете предыдущую версию среды CLR с более новой версией компилятора и когда вы компилируете с параметрами **/clr** и **/GL.**

Для устранения этой ошибки не используйте параметры **/GL** и **/clr** или установите версию среды CLR, которая поставляется с вашим компилятором.

Дополнительные сведения см. в разделах [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) и [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).
