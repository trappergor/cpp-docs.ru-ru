---
title: Аддитивные операторы в C | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- usual arithmetic conversions
- operators [C], addition
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7be460ace4e407a328c0cf23c9e6c9af09d17ca0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101486"
---
# <a name="c-additive-operators"></a>Аддитивные операторы в C

Аддитивные операторы выполняют сложение (**+**) и вычитание (**-**).

## <a name="syntax"></a>Синтаксис

*additive-expression*: *multiplicative-expression*

*additive-expression*  **+**  *multiplicative-expression*

*additive-expression*  **-**  *multiplicative-expression*

> [!NOTE]
>  Хотя синтаксис *выражения-сложения* включает *выражение-умножения*, это не означает, что требуются выражения, в которых используется умножение. Синтаксис *выражения-умножения*, *выражения-приведения* и *унарного выражения* см. в документе [Краткие сведения о синтаксисе языка C](../c-language/c-language-syntax-summary.md).

Операнды могут быть целыми значениями или значениями с плавающей запятой. Некоторые аддитивные операции также можно выполнять со значениями указателя, как описано в разделах, посвященных каждому оператору.

Аддитивные операторы выполняют обычные арифметические преобразования с операндами целочисленного типа и типа с плавающей запятой. После преобразования тип результата совпадает с типом операндов. Поскольку преобразования, выполняемые аддитивными операторами, не обеспечивают условия переполнения или потери значимости, данные могут быть потеряны, если результат аддитивной операции невозможно представить в типе операндов после преобразования.

## <a name="see-also"></a>См. также

[Аддитивные операторы: + и -](../cpp/additive-operators-plus-and.md)