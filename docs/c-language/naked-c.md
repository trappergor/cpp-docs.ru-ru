---
title: "Naked в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 474cb57ced17088c0ce9be8613a9373c702afe69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="naked-c"></a>Naked (C)
**Блок, относящийся только к системам Microsoft**  
  
 Атрибут класса хранения naked является расширением языка C для систем Microsoft. Код функций, объявленных с этим атрибутом, создается компилятором без кода пролога и эпилога. Благодаря этому вы можете вставить в качестве пролога и эпилога свой собственный код на языке ассемблера. Функции с атрибутом naked полезны для написания драйверов виртуальных устройств.  
  
 Дополнительные сведения см. в статье [Функции Naked](../c-language/naked-functions.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)