---
title: Струнная конверсия Макрос
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
ms.openlocfilehash: 8df496b78334d26e7d3664642b2e9d93d6149843
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325843"
---
# <a name="string-conversion-macros"></a>Струнная конверсия Макрос

Эти макросы обеспечивают функции преобразования строк.

## <a name="atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a>ATL и MFC String Преобразование Макрос

Рассматриваемые здесь макросы преобразования строк можно использовать как для ATL, так и для MFC. Для получения дополнительной информации о преобразовании строк MFC см. [TN059: Использование MFC MBCS/Unicode Conversion Macros](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) и [MFC Macros и Globals.](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE и TEXTMETRIC Струнные Преобразования Макрос

Эти макросы создают копию структуры [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) или [TEXTMETRIC](/windows/win32/api/wingdi/ns-wingdi-textmetricw) и преобразуют строки в новой структуре в новый тип строки. Макросы распределять память на стеке для новой структуры и возвращать указатель в новую структуру.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Remarks

Пример:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

and:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

В макро-названиях тип строки в структуре источника находится слева (например, **A),** а тип строки в структуре назначения находится справа (например, **W).** **Стенды** для LPSTR, **OLE** означает LPOLESTR, **T** означает LPTSTR, а **W** - LPWSTR.

Таким образом, DEVMODEA2W `DEVMODE` копирует структуру со `DEVMODE` строками LPSTR в структуру со строками `TEXTMETRIC` LPWSTR, TEXTMETRICOLE2T копирует структуру со строками LPOLESTR в `TEXTMETRIC` структуру со строками LPTSTR и так далее.

Две строки, преобразованные в структуру, `DEVMODE` являются названием устройства ()`dmDeviceName`и названием формы ().`dmFormName` Макроспреобразования `DEVMODE` строки также обновляют`dmSize`размер структуры ().

Четыре строки, преобразованные в `TEXTMETRIC` структуре, являются первым персонажем (),`tmFirstChar`последним персонажем ( ),`tmLastChar`персонажем по умолчанию (),`tmDefaultChar`и персонажем-брейком ().`tmBreakChar`

Поведение макросов преобразования `DEVMODE` строки `TEXTMETRIC` зависит от директивы компилятора, если таковые имеется. Если исходный и конечный типы совпадают, преобразование не выполняется. Директивы компилятора меняют **T** и **OLE** следующим образом:

|Действующая директива компилятора|T становится|OLE становится|
|----------------------------------|---------------|-----------------|
|Нет|**A**|**Ж**|
|**\_Юникода**|**Ж**|**Ж**|
|**OLE2ANSI**|**A**|**A**|
|UNICODE и **OLE2ANSI** ** \_**|**Ж**|**A**|

В следующей `DEVMODE` таблице `TEXTMETRIC` перечислены макросы преобразования строки.

|||
|-|-|
|ДЕВМОДЕА2В|TEXTMETRICA2W|
|ДЕВМОЕНЕОЛЕ2Т|TEXTMETRICOLE2T|
|ДЕВМОТЕТ2OLE|ТЕКСТМЕТРИЯ2OLE|
|ДЕВМОДЕВ2А|TEXTMETRICW2A|

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
