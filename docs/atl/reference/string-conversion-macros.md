---
title: Макросы преобразования строк | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa44449c65dbdfdea93004fa2fe1adffdeba033d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061746"
---
# <a name="string-conversion-macros"></a>Макросы преобразования строк

Эти макросы предоставляют строку функции преобразования.

##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL и макросов преобразования MFC из строки

Рассматриваемые здесь макросы преобразования строк можно использовать как для ATL, так и для MFC. Дополнительные сведения о преобразовании строки MFC см. в разделе [TN059: использование макросов преобразования MFC MBCS в Юникод](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) и [макросы и Globals MFC](../../mfc/reference/mfc-macros-and-globals.md).

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  DEVMODE и макросы преобразования строк TEXTMETRIC

Эти макросы создать копию [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) или [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) структурировать и преобразования строк в новую структуру в новый строковый тип. Макросы выделить память в стеке для новой структуры и возвращают указатель на структуру нового.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Примечания

Пример:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

and:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

В именах макросов тип string в структуре источника — в левой части (например, **объект**) и строковый тип в целевой структуре находится справа (например, **W**). **Объект** расшифровывается LPSTR, **OLE** расшифровывается LPOLESTR, **T** расшифровывается LPTSTR, и **W** расшифровывается LPWSTR.

Таким образом, копирует DEVMODEA2W `DEVMODE` структуру с LPSTR строки в `DEVMODE` структуры со строками LPWSTR, копии TEXTMETRICOLE2T `TEXTMETRIC` структуру с LPOLESTR строки в `TEXTMETRIC` структуры со строками LPTSTR и т. д.

Две строки в `DEVMODE` структуры — это имя устройства (`dmDeviceName`) и имя формы (`dmFormName`). `DEVMODE` Макросы преобразования строк также обновить размер структуры (`dmSize`).

Четыре строки, преобразуются в `TEXTMETRIC` структуры являются первый символ (`tmFirstChar`), последний символ (`tmLastChar`), символ по умолчанию (`tmDefaultChar`) и знака разрыва (`tmBreakChar`).

Поведение `DEVMODE` и `TEXTMETRIC` макросы преобразования строк зависит от директивы компилятора в силу, если таковые имеются. Если исходный и конечный типы совпадают, преобразование не выполняется. Директивы компилятора изменяют **T** и **OLE** следующим образом:

|Действующая директива компилятора|T становится|OLE становится|
|----------------------------------|---------------|-----------------|
|Нет|**A**|**W**|
|**\_ЮНИКОД**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|**\_Юникод** и **OLE2ANSI**|**W**|**A**|

В следующей таблице перечислены `DEVMODE` и `TEXTMETRIC` макросы преобразования строк.

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
