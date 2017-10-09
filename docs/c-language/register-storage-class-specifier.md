---
title: "Описатель класса хранения register | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 95c06471b7d8ea60754c29a9bde3159174e9c194
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="register-storage-class-specifier"></a>Спецификатор класса хранения register
**Блок, относящийся только к системам Майкрософт**  
  
 Компилятор Microsoft C/C++ не учитывает пользовательские запросы на переменные регистра. Но в целях обеспечения переносимости компилятор учитывает всю остальную семантику, связанную с ключевым словом **register**. Например, невозможно применить унарный оператор взятия адреса (**&**) к объекту регистра. Кроме того, ключевое слово **register** невозможно использовать в массивах.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Спецификаторы классов хранения для объявлений внутреннего уровня](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
