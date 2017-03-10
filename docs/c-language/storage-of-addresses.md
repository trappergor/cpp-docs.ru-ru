---
title: "Хранение адресов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 78ed46fc8412f351d46d3a2b4c37348382d7aaa5
ms.lasthandoff: 02/24/2017

---
# <a name="storage-of-addresses"></a>Хранение адресов
Объем хранилища, необходимый для адреса, и значение адреса зависят от реализации компилятора. Одинаковая длина указателей на разные типы не гарантируется. Поэтому значение **sizeof(char \*)** необязательно равно значению **sizeof(int \*)**.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Для компилятора Microsoft C значение **sizeof(char \*)** равно значению **sizeof(int \*)**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Объявления указателей](../c-language/pointer-declarations.md)
