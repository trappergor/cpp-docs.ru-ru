---
title: Использование CString | Документы Microsoft
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5759c8a0aaa628d612010cb7d04690a3d3bfa54f
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238725"
---
# <a name="using-cstring"></a>Использование CString
В следующих подразделах этого раздела описывается программирование с использованием `CString`. Справочную информацию о `CString` класса, см. в документации для [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  
  
 Чтобы использовать `CString`, включите заголовок `atlstr.h`.  
  
 `CString`, `CStringA`, И `CStringW` классы представляют собой специализации шаблона класса [CStringT](../atl-mfc-shared/reference/cstringt-class.md) на основе типа символьных данных.  
  
 Объект `CStringW` содержит тип `wchar_t` и поддерживает строки Юникода. Объект `CStringA` содержит тип `char` и поддерживает строки с однобайтовой и многобайтовой кодировкой. Объект `CString` поддерживает тип `char` или тип `wchar_t` в зависимости от того, какой символ определен во время компиляции — `MBCS` или `UNICODE`.  
  
 Объект `CString` хранит символьные данные в объекте `CStringData`. `CString` принимает `null`-символом строки в стиле C. `CString` отслеживает длину строки для повышения производительности, но он также сохраняет `null` знаку в хранимых символьных данных для поддержки преобразования — LPCWSTR. `CString` При экспорте строки в стиле C, включает завершающий символ null. Можно вставить `null` в других местах в `CString`, но может привести к непредвиденным результатам.  
  
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
 [Базовые операции CString](../atl-mfc-shared/basic-cstring-operations.md)  
 Описывает базовые операции `CString`, включая создание объектов из строковых литералов C, доступ к отдельным символам в `CString`, объединение двух объектов и сравнение объектов `CString`.  
  
 [Управление строковыми данными](../atl-mfc-shared/string-data-management.md)  
 Описывает использование Юникода и многобайтовой кодировки с `CString`.  
  
 [Семантика CString](../atl-mfc-shared/cstring-semantics.md)  
 Поясняет использование объектов `CString`.  
  
 [Операции CString, связанные со строками в стиле C](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 Описывает операции с содержимым объекта `CString` как со строкой с завершающим нулевым байтом в стиле C.  
  
 [Выделение и освобождение памяти для BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 Описывает использование памяти для `BSTR` и COM-объектов.  
  
 [Очистка исключений CString](../atl-mfc-shared/cstring-exception-cleanup.md)  
 Поясняет, что явная очистка в MFC 3.0 и последующих версий больше не требуется.  
  
 [Передача аргументов CString](../atl-mfc-shared/cstring-argument-passing.md)  
 Поясняет, как передать объекты CString в функции и как вернуть объекты `CString` из функций.  
  
 [Поддержка Юникода и многобайтовой кодировки](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 Описывает реализацию поддержки Юникода и многобайтовой кодировки в MFC.  
  
## <a name="reference"></a>Ссылка  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Содержит справочные сведения о классе `CStringT`.  
  
 [Класс CSimpleStringT](../atl-mfc-shared/reference/csimplestringt-class.md)  
 Содержит справочные сведения о классе `CSimpleStringT`.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
 Содержит ссылки на разделы, в которых описаны несколько способов управления строковыми данными.  
  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)

