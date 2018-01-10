---
title: "Строка, управление данными | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad7a17b1b34375fcb45019bcaf8878757288a290
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="string-data-management"></a>Управление строковыми данными
Visual C++ предоставляет несколько способов управления строковыми данными:  
  
-   [Строка, манипуляции](../c-runtime-library/string-manipulation-crt.md) для работы с C-стиле нулем строк  
  
-   Функции Win32 API для управления строками  
  
-   Класс MFC [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md), который предоставляет гибкий и изменяемые строковых объектов  
  
-   Класс [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md), который предоставляет объект, строка зависящие от MFC с такой же функциональностью, как`CString`  
  
 Почти все программы работы со строковыми данными. MFC `CString` класс часто является оптимальным решением для обработки гибкие строк. Начиная с версии 7.0, `CString` может использоваться в приложениях MFC или зависящие от MFC. Библиотеки времени выполнения и `CString` поддерживает строки, содержащие многобайтовые символы (расширенный), как в программировании Юникода и MBCS.  
  
 В этой статье описаны службы общего назначения, библиотека классов предоставляет связанные с строками. В этой статье рассматриваются:  
  
-   [Переносимость Юникода и многобайтовой Кодировки предоставляют](#_core_unicode_and_mbcs_provide_portability)  
  
-   [CStrings и указатели const char](#_core_cstrings_and_const_char_pointers)  
  
-   [Подсчет ссылок CString](#_core_cstring_reference_counting)  
  
 [Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md) класс обеспечивает поддержку управления строками. Он предназначен для замены и расширения функциональных возможностей пакета строка библиотеки времени выполнения C обычным образом. `CString` Класс предоставляет функции-члены и операторы для обработки упрощенный строки, аналогичные используемым в Basic. Класс также предоставляет конструкторы и операторы для конструирования, назначение и сравнение **CStrings** и standard C++ строковых типов данных. Поскольку `CString` не является производным от `CObject`, можно использовать `CString` объектов независимо от большинства библиотеки классов Microsoft Foundation (MFC).  
  
 `CString`объекты следуют «value семантики». Объект `CString` представляет уникальное значение. Представьте `CString` виде фактические строки, а не как указатель на строку.  
  
 Объект `CString` объект представляет последовательность с переменным числом символов. `CString`объекты могут рассматриваться как массивы символов.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a>Юникод и многобайтовая Кодировка предоставляют переносимости  
 С MFC версии 3.0 и более поздних, MFC, включая `CString`, включена поддержка Юникода и многобайтовой кодировке (MBCS). Эта поддержка упрощает для написания переносимого приложений, вы можете создать для символов Юникода или ANSI. Чтобы включить этот переносимость каждый символ в `CString` объект имеет тип **TCHAR**, определяется как `wchar_t` при определении символа **_UNICODE** при построении приложения или в виде `char` в противном случае. Объект `wchar_t` символ имеет ширину 16 бит. Многобайтовые Кодировки доступен в том случае, если сборка с символом **_MBCS** определен. MFC строится при помощи либо **_MBCS** символ (для библиотеки NAFX) или **_UNICODE** символ (для библиотек UAFX) определен.  
  
> [!NOTE]
>  `CString` Примеры в этом и сопутствующие статьи на содержат строк, правильный формат строковых литералов для обеспечения переносимости Юникода, с помощью **_T** макросом, который преобразует строковые литералы формы:  
  
 `L"literal string"`  
  
> [!NOTE]
>  который компилятор обрабатывает как строка Юникода. Например, приведенный ниже код  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]  
  
> [!NOTE]
>  преобразуется в виде строки в Юникоде, если **_UNICODE** определяется или как ANSI строки, если оно не. Дополнительные сведения см. в статье [задать многобайтовых символов (MBCS) поддержка Юникода и](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
 Объект `CString` объект может хранить до **INT_MAX** (2 147 483 647) символов. **TCHAR** тип данных используется для получения или задания отдельных символов внутри `CString` объекта. В отличие от массивов знаков `CString` класс имеет возможность выделения встроенной памяти. Это позволяет `CString` объектов автоматически расти по мере необходимости (то есть у вас беспокоиться о растет `CString` объекта под длинных строк).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a>CStrings и указатели const char  
 A `CString` объект также может действовать как строковый литерал C-стиле ( `PCXSTR`, который является таким же, как **const char\* ** if не в Юникоде). [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) позволяет оператор преобразования `CString` объектов должен быть замещен свободно указатели на расширенные символы в вызовах функций. **CString (— LPCWSTR** `pszSrc` **)** конструктор позволяет указатели символ должен быть замещен `CString` объектов.  
  
 Не производится попыток для свертки `CString` объектов. Если создать две `CString` объектов содержащий `Chicago`, например, символы в `Chicago` хранятся в двух местах. (Это может оказаться верно для будущих версий MFC, поэтому не следует полагаться на него.)  
  
> [!NOTE]
>  Используйте [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) функций-членов. когда требуется прямой доступ к `CString` как неконстантных указатель на символ.  
  
> [!NOTE]
>  Используйте [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) и [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) функции-члены для выделения и задать `BSTR` объекты, используемые в автоматизация (ранее известная как OLE-автоматизация).  
  
> [!NOTE]
>  Если это возможно, следует выделить `CString` объекты в кадре, а не в куче. Это экономит память и упрощает передачи параметров.  
  
 `CString` Класса не реализованы как библиотеки классов Microsoft Foundation класса коллекции, хотя `CString` объектов определенно могут храниться как элементы в коллекции.  
  
##  <a name="_core_cstring_reference_counting"></a>Подсчет ссылок CString  
 Начиная с версии 4.0, MFC при [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md) копируются объекты, MFC увеличивает счетчик ссылок, а не копируя данные. Это делает передача параметров по значению и возвращение `CString` объектов по значению более эффективно. Эти операции вызывают конструктор копии для вызова, иногда несколько раз. Увеличение счетчика ссылок снизить эту нагрузку для этих общих операций и с помощью `CString` более привлекательным вариантом.  
  
 Поскольку каждая копия уничтожается, счетчик ссылок в исходном объекте уменьшается. Исходный `CString` объект не удаляется, пока его счетчик ссылок уменьшается до нуля.  
  
 Можно использовать `CString` функции-члены [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) для отключения или включения подсчета ссылок.  
  
## <a name="see-also"></a>См. также  
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)

