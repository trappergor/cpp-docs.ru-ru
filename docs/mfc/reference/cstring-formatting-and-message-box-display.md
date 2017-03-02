---
title: "Форматирование CString и отображение окна сообщения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects, formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 48fc79f74bda10e43807d57fbcd7ed85fbb5d78b
ms.lasthandoff: 02/24/2017

---
# <a name="cstring-formatting-and-message-box-display"></a>Форматирование CString и отображение окна сообщения
Ряд функций, позволяющих форматирования и синтаксического анализа `CString` объектов. Эти функции можно использовать всякий раз, когда приходится манипулировать `CString` объектов, но они особенно полезны для форматирования строк, которые будут отображаться в текстовом окне сообщения.  
  
 Эта группа функций также содержит глобальные подпрограммы для отображения окна сообщения.  
  
### <a name="cstring-functions"></a>Функции CString  
  
|||  
|-|-|  
|[AfxExtractSubString](#afxextractsubstring)|Извлечение подстрок, разделенных один знак из заданной исходной строки.|  
|[AfxFormatString1](#afxformatstring1)|Замещает заданной строки для форматирования символов «%1» в строке содержится в таблице строк.|  
|[AfxFormatString2](#afxformatstring2)|Замещает двух строк для формата символы «%1» и «%2» в строке содержится в таблице строк.|  
|[AfxMessageBox](#afxmessagebox)|Отображает окно сообщения.|  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxextractsubstringa--afxextractsubstring"></a><a name="afxextractsubstring"></a>AfxExtractSubString  
 Эту глобальную функцию можно извлечь подстроку из заданной исходной строки.  
  
```   
BOOL AFXAPI AfxExtractSubString (
    CString& rString,  
    LPCTSTR lpszFullString,  
    int iSubString,  
    TCHAR chSep  = '\n'); 
```  
  
### <a name="parameters"></a>Параметры  
 *rString*  
 -   Ссылка на [CString](../../atl-mfc-shared/using-cstring.md) объекта, который будет получать отдельные подстроки.  
  
 *lpszFullString*  
 -   Строка, содержащая полный текст для извлечения из строки.  
  
 *iSubString*  
 -   Отсчитываемый от нуля индекс подстроки, которую требуется извлечь из *lpszFullString*.  
  
 *chSep*  
 -   Разделитель, используемый для разделения подстрок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если функция успешно извлечь подстроку по указанному индексу; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для извлечения нескольких подстрок из исходной строки, если известных один символ, разделяющий каждой подстроке. Эта функция выполняет поиск с начала `lpszFullString` параметр при каждом вызове.  
  
 Эта функция возвращает значение FALSE, если `lpszFullString` равен **NULL** или функция достигает конца `lpszFullString` без поиск `iSubString`+&1; вхождений указанным знаком-разделителем. `rString` Параметр не будет изменен исходное значение, если `lpszFullString` было задано значение **NULL**; в противном случае — `rString` параметру присваивается пустая строка, если не удалось извлечь подстроку с указанным индексом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#48;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxformatstring1a--afxformatstring1"></a><a name="afxformatstring1"></a>AfxFormatString1  
 Замена строки, на который указывает `lpsz1` для любых экземпляров символы «%1» в шаблон строковый ресурс, идентифицируемый `nIDS`.  
  
```  
void  AfxFormatString1(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1); 
```  
  
### <a name="parameters"></a>Параметры  
 `rString`  
 Ссылку на `CString` объект, который будет содержать результирующие строки после выполнения подстановки.  
  
 `nIDS`  
 Идентификатор ресурса строки шаблона, на котором выполняется замена.  
  
 `lpsz1`  
 Строка, которая заменит формат символы «%1» в строке шаблона.  
  
### <a name="remarks"></a>Примечания  
 Вновь сформированной строка хранится в `rString`. Например, если строка в таблице строк — «Файл %1 не найден» и `lpsz1` равно «C:\MYFILE. TXT», затем `rString` будет содержать строку «файл C:\MYFILE. TXT не найден». Эта функция полезна для форматирования строк, отправляемых в окнах сообщений и других окнах.  
  
 Появление символы форматирования «%1» в строке несколько раз, выполняются несколько подстановок.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#25;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxformatstring2a--afxformatstring2"></a><a name="afxformatstring2"></a>AfxFormatString2  
 Замена строки, на который указывает `lpsz1` для любых экземпляров символы «%1» и строка, на который указывает `lpsz2` для любых экземпляров символы «%2», в шаблон строковый ресурс, идентифицируемый `nIDS`.  
  
```   
void AfxFormatString2(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1,  
    LPCTSTR lpsz2); 
```  
  
### <a name="parameters"></a>Параметры  
 `rString`  
 Ссылку на `CString` , содержащий результирующие строки после выполнения подстановки.  
  
 `nIDS`  
 Идентификатор строки таблицы строки шаблона, на котором выполняется замена.  
  
 `lpsz1`  
 Строка, которая заменит формат символы «%1» в строке шаблона.  
  
 `lpsz2`  
 Строка, которая заменит формат символы «%2» в строке шаблона.  
  
### <a name="remarks"></a>Примечания  
 Вновь сформированной строка хранится в `rString`. Например, если строка в таблице строк — «Файл %1 не найден в каталоге %2» `lpsz1` указывает на «MYFILE. TXT» и `lpsz2` указывает на «C:\MYDIR», затем `rString` будет содержать строку «файл MYFILE. TXT, не найден в каталоге C:\MYDIR»  
  
 Если формат символов «%1» и «%2» отображаются в строке несколько раз, будет выполнен несколько подстановок. Они не должны быть в числовом порядке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#26;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxmessageboxa--afxmessagebox"></a><a name="afxmessagebox"></a>AfxMessageBox  
 Отображает окно сообщения на экране.  
  
```  
int AfxMessageBox(
    LPCTSTR lpszText,  
    UINT nType = MB_OK,  
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,  
    UINT nType = MB_OK,  
    UINT nIDHelp = (UINT) -1); 
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указывает на `CString` объект или нулем строка, содержащая сообщение, отображаемое в окне сообщения.  
  
 `nType`  
 Стиль окна сообщения. Применить любой из [стили окна сообщений](../../mfc/reference/message-box-styles.md) в поле.  
  
 `nIDHelp`  
 Идентификатор контекста справки для данного сообщения; 0 указывает, что будет использоваться контекст справки приложения по умолчанию.  
  
 `nIDPrompt`  
 Уникальный идентификатор, используемый для ссылки на строку в таблице строк.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если не хватает памяти для отображения окна сообщений. в противном случае возвращается одно из следующих значений:  
  
- **IDABORT** выбран вариант аварийного завершения.  
  
- **IDCANCEL** была выбрана кнопка отмены.  
  
- **IDIGNORE** выбран вариант игнорировать.  
  
- **IDNO** выбран вариант Нет.  
  
- **IDOK** была выбрана кнопка ОК.  
  
- **IDRETRY** выбран вариант, повторите попытку.  
  
- **IDYES** выбран вариант Да.  
  
 Если окно сообщения содержит кнопки "Отмена", **IDCANCEL** будет возвращено значение, если нажата клавиша ESC или кнопку "Отмена". Если окно сообщения содержит кнопки "Отмена", нажав клавишу ESC не оказывает влияния.  
  
 Функции [AfxFormatString1](#afxformatstring1) и [AfxFormatString2](#afxformatstring2) можно использовать для форматирования текста, отображаемого в окне сообщения.  
  
### <a name="remarks"></a>Примечания  
 Первая форма перегруженные функции отображает строку текста, на который указывает `lpszText` в окне сообщения и использует `nIDHelp` для описания контекста справки. Контекст справки используется для перехода к соответствующие разделы справки, когда пользователь нажимает клавишу справки (обычно F1).  
  
 Вторая форма функция использует строковый ресурс с Идентификатором `nIDPrompt` для отображения сообщения в окне сообщения. Соответствующая страница справки находится до значения `nIDHelp`. Если значение по умолчанию `nIDHelp` используется (â € 1»), идентификатор строкового ресурса `nIDPrompt`, используемый для контекста справки. Дополнительные сведения об определении контекстами справки см. в разделе [Технические заметки 28](../../mfc/tn028-context-sensitive-help-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#133;](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)

