---
title: "codecvt_utf8 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.codecvt_utf8
- std::codecvt_utf8
- codecvt_utf8
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 1f6c2724747d22aa662779fa8f6433647a7853f3
ms.lasthandoff: 02/24/2017

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

