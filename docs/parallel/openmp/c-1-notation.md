---
title: C.1 нотация | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a23b2631-8096-4bf3-ac23-ba4f4bd7a52a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bbb3190dd5aa32315cd8f402f92fd94893b4b27
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411876"
---
# <a name="c1-notation"></a>C.1 Нотация

Грамматические правила состоят из имени для нетерминального, за которым следует двоеточие, следуют альтернативные варианты замены в отдельных строках.

Термин синтаксические выражения<sub>opt</sub> указывает, что термин не является обязательным в замены.

Синтаксические выражения *термин*<sub>optseq</sub> эквивалентен *термин seq*<sub>opt</sub> с следующие дополнительные правила:

*Термин seq* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Термин*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Термин seq* *термин*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Термин seq* **,** *термин*