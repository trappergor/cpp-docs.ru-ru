---
title: "&lt;fstream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <fstream>
dev_langs:
- C++
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e479caecbca33a19854f6800a037eb093d0b2f5a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;
Определяет несколько классов, поддерживающих операции iostreams для последовательностей, хранящихся во внешних файлах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <fstream>  
  
```  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Тип `basic_filebuf`, специализированный на параметрах шаблона `char`.|  
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Тип `basic_fstream`, специализированный на параметрах шаблона `char`.|  
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Тип `basic_ifstream`, специализированный на параметрах шаблона `char`.|  
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Тип `basic_ofstream`, специализированный на параметрах шаблона `char`.|  
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Тип `basic_fstream`, специализированный на параметрах шаблона `wchar_t`.|  
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Тип `basic_ifstream`, специализированный на параметрах шаблона `wchar_t`.|  
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Тип `basic_ofstream`, специализированный на параметрах шаблона `wchar_t`.|  
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Тип `basic_filebuf`, специализированный на параметрах шаблона `wchar_t`.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Класс шаблона описывает буфер потока, который управляет передачей элементов типа **Elem**, признаки символов которого определяются с помощью класса **Tr**, в последовательность элементов, сохраненную во внешнем файле, и из нее.|  
|[basic_fstream](../standard-library/basic-fstream-class.md)|Класс шаблона описывает объект, управляющий извлечением и вставкой элементов и закодированных объектов с помощью буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**.|  
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Класс шаблона описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**.|  
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Класс шаблона описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)



