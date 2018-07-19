---
title: Naked в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a60cdec00f3109bfcc332feeaca24ba5d6880f9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383122"
---
# <a name="naked-c"></a>Naked (C)
**Блок, относящийся только к системам Microsoft**  
  
 Атрибут класса хранения naked является расширением языка C для систем Microsoft. Код функций, объявленных с этим атрибутом, создается компилятором без кода пролога и эпилога. Благодаря этому вы можете вставить в качестве пролога и эпилога свой собственный код на языке ассемблера. Функции с атрибутом naked полезны для написания драйверов виртуальных устройств.  
  
 Дополнительные сведения см. в статье [Функции Naked](../c-language/naked-functions.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)