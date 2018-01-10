---
title: "Хранение адресов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd82f6f5046cf910fbc871be37d4af5856796792
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-addresses"></a>Хранение адресов
Объем хранилища, необходимый для адреса, и значение адреса зависят от реализации компилятора. Одинаковая длина указателей на разные типы не гарантируется. Поэтому значение **sizeof(char \*)** необязательно равно значению **sizeof(int \*)**.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Для компилятора Microsoft C значение **sizeof(char \*)** равно значению **sizeof(int \*)**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Объявления указателей](../c-language/pointer-declarations.md)