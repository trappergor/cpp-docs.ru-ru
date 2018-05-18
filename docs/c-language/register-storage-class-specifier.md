---
title: Описатель класса хранения register | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 211f623923286e598f495920bcbdac3a9321b13a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="register-storage-class-specifier"></a>Спецификатор класса хранения register
**Блок, относящийся только к системам Майкрософт**  
  
 Компилятор Microsoft C/C++ не учитывает пользовательские запросы на переменные регистра. Но в целях обеспечения переносимости компилятор учитывает всю остальную семантику, связанную с ключевым словом **register**. Например, невозможно применить унарный оператор взятия адреса (**&**) к объекту регистра. Кроме того, ключевое слово **register** невозможно использовать в массивах.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Спецификаторы классов хранения для объявлений внутреннего уровня](../c-language/storage-class-specifiers-for-internal-level-declarations.md)