---
title: Использование CString
ms.date: 06/18/2018
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
ms.openlocfilehash: a84ae21b60d87971cb2f7b758dd369b4078607e6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740307"
---
# <a name="using-cstring"></a>Использование CString

В следующих подразделах этого раздела описывается программирование с использованием `CString`. Справочную документацию по `CString` класса, см. в документации [CStringT](../atl-mfc-shared/reference/cstringt-class.md).

Чтобы использовать `CString`, включите заголовок `atlstr.h`.

`CString`, `CStringA`, И `CStringW` классы представляют собой специализации шаблона класса [CStringT](../atl-mfc-shared/reference/cstringt-class.md) на основе типа символьных данных, они поддерживают.

Объект `CStringW` объект содержит **wchar_t** введите и поддерживает строки Юникода. Объект `CStringA` объект содержит **char** типа и строки поддерживает с однобайтовой и многобайтовой кодировкой (MBCS). Объект `CString` объект поддерживает **char** тип или `wchar_t` тип, в зависимости от того, определен ли во время компиляции символов MBCS или символом ЮНИКОДА.

Объект `CString` хранит символьные данные в объекте `CStringData`. `CString` принимает строки НУЛЕВЫМ байтом В стиле. `CString` отслеживает строка длины для повышения производительности, но он также сохраняет нуль-символ в хранимых символьных данных для поддержки преобразования LPCWSTR. `CString` включает знак завершения null при экспорте строка C-стиля. Можно вставить значение NULL в других местах `CString`, но он может привести к непредвиденным результатам.

Следующий набор строковых классов можно использовать без привязки библиотеки MFC, как с поддержкой CRT, так и без нее: `CAtlString`, `CAtlStringA` и `CAtlStringW`.

`CString` используется в машинных проектах. Для проектов с управляемым кодом (C++/CLI) используйте `System::String`.

Чтобы добавить больше возможностей, чем предлагает `CString`, `CStringA` или `CStringW`, необходимо создать подкласс `CStringT`, содержащий дополнительные компоненты.

В следующем коде показано создание `CString` и его распечатка в стандартном выводе:

```cpp
#include <atlstr.h>

int main() {
    CString aCString = CString(_T("A string"));
    _tprintf(_T("%s"), (LPCTSTR) aCString);
}
```

## <a name="in-this-section"></a>В этом разделе

[Базовые операции CString](../atl-mfc-shared/basic-cstring-operations.md)<br/>
Описывает базовые операции `CString`, включая создание объектов из строковых литералов C, доступ к отдельным символам в `CString`, объединение двух объектов и сравнение объектов `CString`.

[Управление строковыми данными](../atl-mfc-shared/string-data-management.md)<br/>
Описывает использование Юникода и многобайтовой кодировки с `CString`.

[Семантика CString](../atl-mfc-shared/cstring-semantics.md)<br/>
Поясняет использование объектов `CString`.

[Операции CString, связанные со строками в стиле C](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
Описывает операции с содержимым объекта `CString` как со строкой с завершающим нулевым байтом в стиле C.

[Выделение и освобождение памяти для BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)<br/>
Описывает использование памяти для BSTR и COM-объектов.

[Очистка исключений CString](../atl-mfc-shared/cstring-exception-cleanup.md)<br/>
Поясняет, что явная очистка в MFC 3.0 и последующих версий больше не требуется.

[Передача аргументов CString](../atl-mfc-shared/cstring-argument-passing.md)<br/>
Поясняет, как передать объекты CString в функции и как вернуть объекты `CString` из функций.

[Поддержка Юникода и многобайтовой кодировки](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)<br/>
Описывает реализацию поддержки Юникода и многобайтовой кодировки в MFC.

## <a name="reference"></a>Ссылка

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Содержит справочные сведения о классе `CStringT`.

[Класс CSimpleStringT](../atl-mfc-shared/reference/csimplestringt-class.md)<br/>
Содержит справочные сведения о классе `CSimpleStringT`.

## <a name="related-sections"></a>Связанные разделы

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
Содержит ссылки на разделы, в которых описаны несколько способов управления строковыми данными.

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
