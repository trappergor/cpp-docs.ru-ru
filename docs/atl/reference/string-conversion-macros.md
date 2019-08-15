---
title: Макросы преобразования строк
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: f7d9548fc5710e8d3d5d668dff230a60e7a291a1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495182"
---
# <a name="string-conversion-macros"></a>Макросы преобразования строк

Эти макросы предоставляют функции преобразования строк.

##  <a name="atl_and_mfc_string_conversion_macros"></a>Макросы преобразования строк ATL и MFC

Рассматриваемые здесь макросы преобразования строк можно использовать как для ATL, так и для MFC. Дополнительные сведения о преобразовании строк MFC см. [в разделе TN059: Использование макросов](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) для преобразования многобайтовой кодировки и Юникода и [макросов MFC и глобальных библиотек](../../mfc/reference/mfc-macros-and-globals.md).

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>Макросы преобразования строк DEVMODE и ТЕКСТМЕТРИК

Эти макросы создают копию структуры [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) или [текстметрик](/windows/win32/api/wingdi/ns-wingdi-textmetricw) и преобразуют строки в новой структуре в новый строковый тип. Макросы выделяют память в стеке для новой структуры и возвращают указатель на новую структуру.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Примечания

Например:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

and:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

В именах макросов строковый тип в исходной структуре находится слева (например,), а типстроки в целевой структуре — справа (например, **W**). **А** означает LPSTR, **OLE** означает ЛПОЛЕСТР, **T** означает LPTSTR, а **W** — для LPWSTR.

Таким образом, DEVMODEA2W копирует `DEVMODE` структуру с строками LPSTR `DEVMODE` в структуру со `TEXTMETRIC` строками LPWSTR, TEXTMETRICOLE2T копирует структуру с лполестр строками в `TEXTMETRIC` структуру с строками LPTSTR и т. д.

Две строки, преобразованные в `DEVMODE` структуру, — это имя устройства`dmDeviceName`() и имя формы (`dmFormName`). Макросы преобразования`dmSize` строктакжеобновляютразмер`DEVMODE` структуры ().

Четыре строки, преобразованные в `TEXTMETRIC` структуру, являются первым символом`tmFirstChar`(), последним символом`tmLastChar`(), символом по`tmDefaultChar`умолчанию () и символом`tmBreakChar`разрыва ().

Поведение `DEVMODE` макросов преобразования строк `TEXTMETRIC` и зависит от применяемой директивы компилятора (при наличии). Если исходный и конечный типы совпадают, преобразование не выполняется. Директивы компилятора меняются **T** и **OLE** следующим образом:

|Действующая директива компилятора|T становится|OLE становится|
|----------------------------------|---------------|-----------------|
|none|**A**|**W**|
|**\_ЮНИКОД**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|Юникод и **OLE2ANSI**  **\_**|**W**|**A**|

В следующей таблице перечислены `DEVMODE` макросы и `TEXTMETRIC` преобразования строк.

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
