---
title: "Класс wbuffer_convert | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::cvt::wbuffer_convert
- wbuffer_convert
- cvt::wbuffer_convert
- wbuffer/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 8efbf80606e1196b7376a264e63b87e89e07b53d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

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
  
|Параметр|Описание|  
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

