---
title: "codecvt_utf8 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt/std::codecvt_utf8
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 873a4e1834b13ac69370223339dd395b650eb679
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="codecvtutf8"></a>codecvt_utf8
Представляет аспект [языкового стандарта](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-8.

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Параметры

`Elem`  
Тип двухбайтового элемента.  
`Maxcode`  
Максимальное количество символов для аспекта языкового стандарта.  
`Mode`  
Сведения о конфигурации для аспекта языкового стандарта.  

## <a name="remarks"></a>Примечания

Поток байтов может записываться в двоичный файл или текстовый файл.  

## <a name="requirements"></a>Требования

Заголовок: <codecvt> Пространство имен: std

