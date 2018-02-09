---
title: "Преобразования из других типов | Документация Майкрософт"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30021ad4058eed7d9fbca31b8e3d3141a55987f2
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
# <a name="conversions-from-other-types"></a>Преобразования из других типов

Так как значение **enum** по определению имеет тип **int**, преобразования в тип **enum** и обратно выполняются так же, как и для типа **int**. В компиляторе Microsoft C тип integer обозначает то же самое, что и **long**.

**Блок, относящийся только к системам Microsoft**

Преобразование между типами структуры и объединения не допускаются.

Любое значение можно преобразовать в тип **void**, но результат такого преобразования можно использовать только в контексте, в котором значение выражения отбрасывается, например в операторе выражения.

Тип **void** по определению не имеет значения. Поэтому его невозможно преобразовать ни в какой другой тип, а другие типы невозможно преобразовать в **void** путем присваивания. Но значение можно явным образом привести к типу **void**, как описано в статье [Преобразования с приведением типов](../c-language/type-cast-conversions.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Преобразования назначений](../c-language/assignment-conversions.md)  
