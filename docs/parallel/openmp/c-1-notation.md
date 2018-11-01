---
title: C.1 Нотация
ms.date: 11/04/2016
ms.assetid: a23b2631-8096-4bf3-ac23-ba4f4bd7a52a
ms.openlocfilehash: 593450b6dd7dcb30adbf8546ad96ff716c6fbc1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473987"
---
# <a name="c1-notation"></a>C.1 Нотация

Грамматические правила состоят из имени для нетерминального, за которым следует двоеточие, следуют альтернативные варианты замены в отдельных строках.

Термин синтаксические выражения<sub>opt</sub> указывает, что термин не является обязательным в замены.

Синтаксические выражения *термин*<sub>optseq</sub> эквивалентен *термин seq*<sub>opt</sub> с следующие дополнительные правила:

*Термин seq* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Термин*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Термин seq* *термин*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Термин seq* **,** *термин*