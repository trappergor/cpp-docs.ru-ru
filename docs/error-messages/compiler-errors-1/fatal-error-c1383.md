---
title: Неустранимая ошибка C1383
ms.date: 11/04/2016
f1_keywords:
- C1383
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
ms.openlocfilehash: 4ab96c0516ee5593a969669c03ae22f0c211ae27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208587"
---
# <a name="fatal-error-c1383"></a>Неустранимая ошибка C1383

параметр компилятора /GL несовместим с установленной версией среды CRL

Ошибка C1383 происходит, когда вы используете предыдущую версию среды CLR с более новой версией компилятора и когда вы компилируете с параметрами **/clr** и **/GL.**

Для устранения этой ошибки не используйте параметры **/GL** и **/clr** или установите версию среды CLR, которая поставляется с вашим компилятором.

Дополнительные сведения см. в разделах [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) и [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).