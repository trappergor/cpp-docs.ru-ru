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
ms.sourcegitcommit: 89790d1a56f64e6479ae32d72c529142ba8df1de
ms.openlocfilehash: 0dce243b0f7db087db908d603e6cd1cfc4b02db8
ms.lasthandoff: 02/24/2017

---
# <a name="string-conversion-macros"></a>Макросы преобразования строк
Эти макросы обеспечивают строки функции преобразования.  
  
|||  
|-|-|  
|[ATL и макросы преобразования строк в MFC](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)|Набор макросов, которые преобразование между строковыми типами.|  
|[DEVMODE и макросы преобразования строк TEXTMETRIC](http://msdn.microsoft.com/library/85cebec0-2a18-48e5-9c1c-99d5b7f15425)|Набор макросов, которые преобразуют строки в `DEVMODE` и `TEXTMETRIC` структур.|  
  
##  <a name="a-nameatlandmfcstringconversionmacrosa--atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a>ATL и макросы преобразования строк в MFC  
 Рассматриваемые здесь макросы преобразования строк можно использовать как для ATL, так и для MFC. Дополнительные сведения о преобразовании строки MFC см. в разделе [TN059: использование макросов преобразования MFC MBCS в Юникод](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) и [макросов MFC и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md).  
  
##  <a name="a-namedevmodeandtextmetricstringconversionmacrosa--devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE и макросы преобразования строк TEXTMETRIC  
 Эти макросы создать копию [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) или [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) структуры и преобразования строки в новую структуру новый строковый тип. Макросы выделения памяти в стеке для новой структуры и вернуть указатель в новую структуру.  
  
```
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>Примечания  
 Пример:  
  
 [!code-cpp[NVC_ATL_Utilities&#128;](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
 and:  
  
 [!code-cpp[NVC_ATL_Utilities&#129;](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
 В именах макросов тип строки в структуре источника расположен слева (например, **A**) и тип строки в структуре назначения — справа (например, **W**). **A** stands for **LPSTR**, **OLE** stands for `LPOLESTR`, **T** stands for `LPTSTR`, and **W** stands for `LPWSTR`.  
  
 Таким образом `DEVMODEA2W` копии `DEVMODE` структура с **LPSTR** строки в `DEVMODE` структура с `LPWSTR` строк, `TEXTMETRICOLE2T` копии `TEXTMETRIC` структура с `LPOLESTR` строки в `TEXTMETRIC` структура с `LPTSTR` строк и т. д.  
  
 Две строки преобразуются в `DEVMODE` структуры — это имя устройства ( **dmDeviceName**) и имя формы ( **dmFormName**). `DEVMODE` Макросы преобразования строк также обновить размер структуры ( **dmSize**).  
  
 Четыре строки преобразуются в `TEXTMETRIC` структуры являются первым символом ( **tmFirstChar**), последний знак ( **tmLastChar**), символ по умолчанию ( **tmDefaultChar**) и знак разрыва ( **tmBreakChar**).  
  
 Поведение `DEVMODE` и `TEXTMETRIC` макросы преобразования строк зависит от директивы компилятора в силу, при их наличии. Если исходный и конечный типы совпадают, преобразование не выполняется. Директивы компилятора изменяют **T** и **OLE** следующим образом:  
  
|Действующая директива компилятора|T становится|OLE становится|  
|----------------------------------|---------------|-----------------|  
|Нет|**A**|**W**|  
|**_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**_UNICODE** и **OLE2ANSI**|**W**|**A**|  
  
 В следующей таблице перечислены `DEVMODE` и `TEXTMETRIC` макросы преобразования строк.  
  
### <a name="devmode-and-textmetric-string-conversion-macros"></a>DEVMODE и макросы преобразования строк TEXTMETRIC  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)


