---
title: "Класс wbuffer_convert | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0153bf7d40dbd4290900d15b6e68d84d0c07869
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="wbufferconvert-class"></a>Класс wbuffer_convert
Описывает буфер потока, который управляет передачей элементов в буфер потока байтов и из него.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`Codecvt`|Аспект [языкового стандарта](../standard-library/locale-class.md), представляющий объект преобразования.|  
|`Elem`|Тип двухбайтового элемента.|  
|`Traits`|Признаки, связанные с *Elem*.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс шаблона описывает буфер потока, который управляет передачей элементов типа `_Elem`, признаки символов которого описываются с помощью класса `Traits`, в буфер потока байтов типа `std::streambuf` и из него.  
  
 Преобразование между последовательностями значений `Elem` и многобайтовыми последовательностями выполняется объектом класса `Codecvt<Elem, char, std::mbstate_t>`, который соответствует требованиям аспекта стандартного преобразования кода `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 Объект этого класса шаблона сохраняет:  
  
-   указатель на базовый буфер потока байтов;  
  
-   Указатель на выделенный объект преобразования (освобождается при уничтожении объекта [wbuffer_convert](../standard-library/wbuffer-convert-class.md))
