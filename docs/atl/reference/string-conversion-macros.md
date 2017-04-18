---
title: "Макросы преобразования строк | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: e322c3af297c288ec6c9ccdb1c04e58d0a5759ff
ms.lasthandoff: 04/12/2017

---
# <a name="string-conversion-macros"></a>Макросы преобразования строк
Эти макросы обеспечивают строка функции преобразования.  
  
 
##  <a name="atl_and_mfc_string_conversion_macros"></a>ATL и MFC макросы преобразования строк  
 Рассматриваемые здесь макросы преобразования строк можно использовать как для ATL, так и для MFC. Дополнительные сведения о преобразовании строки MFC см. в разделе [TN059: использование макросов преобразования MFC MBCS в Юникод](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) и [макросов MFC и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md).  
  
##  <a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE и макросы преобразования строк TEXTMETRIC  
 Эти макросы создать копию [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) или [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) структуры и преобразования строк в новой структуре новый строковый тип. Макросы выделение памяти в стеке для новой структуры и вернуть указатель на структуру нового.  
  
```
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>Примечания  
 Например:  
  
 [!code-cpp[NVC_ATL_Utilities #128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
 and:  
  
 [!code-cpp[NVC_ATL_Utilities #129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
 В именах макросов тип string в структуре источника находится слева (например, **A**) и строкового типа в целевой структуре — справа (например, **W**). **A** stands for **LPSTR**, **OLE** stands for `LPOLESTR`, **T** stands for `LPTSTR`, and **W** stands for `LPWSTR`.  
  
 Таким образом `DEVMODEA2W` копии `DEVMODE` структура с **LPSTR** строки в `DEVMODE` структура с `LPWSTR` строк, `TEXTMETRICOLE2T` копии `TEXTMETRIC` структура с `LPOLESTR` строки в `TEXTMETRIC` структура с `LPTSTR` строк и т. д.  
  
 Две строки преобразуются в `DEVMODE` структуры — это имя устройства ( **dmDeviceName**) и имя формы ( **dmFormName**). `DEVMODE` Макросы преобразования строк также обновить размер структуры ( **dmSize**).  
  
 Четыре строки, преобразуются в `TEXTMETRIC` структуры являются первым символом ( **tmFirstChar**), последним символом ( **tmLastChar**), символ по умолчанию ( **tmDefaultChar**) и символа разрыва ( **tmBreakChar**).  
  
 Поведение `DEVMODE` и `TEXTMETRIC` макросы преобразования строк зависит от директивы компилятора в силу, если таковые имеются. Если исходный и конечный типы совпадают, преобразование не выполняется. Директивы компилятора изменяют **T** и **OLE** следующим образом:  
  
|Действующая директива компилятора|T становится|OLE становится|  
|----------------------------------|---------------|-----------------|  
|Нет|**A**|**W**|  
|**_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**_UNICODE** и **OLE2ANSI**|**W**|**A**|  
  
 В следующей таблице перечислены `DEVMODE` и `TEXTMETRIC` макросы преобразования строк.  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)


