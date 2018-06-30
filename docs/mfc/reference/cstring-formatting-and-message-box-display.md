---
title: Форматирование CString и отображение окна сообщения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0367caf33eea9832d33e4e4ec96144d51b1c5c3
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122268"
---
# <a name="cstring-formatting-and-message-box-display"></a>Форматирование CString и отображение окна сообщения
Ряд функций, позволяющих форматирования и синтаксического анализа `CString` объектов. Эти функции можно использовать всякий раз, когда приходится манипулировать `CString` объектов, но они особенно полезны для форматирования строки, которые будут отображаться в текстовое окно сообщения.  
  
 Эта группа функций также содержит глобальные подпрограммы для отображения окна сообщения.  
  
### <a name="cstring-functions"></a>Функции CString  
  
|||  
|-|-|  
|[AfxExtractSubString](#afxextractsubstring)|Извлечение подстрок, разделенные один символ из заданной исходной строки.|  
|[AfxFormatString1](#afxformatstring1)|Замещает заданную строку для форматирования символов «%1» в строке содержится в таблице строк.|  
|[AfxFormatString2](#afxformatstring2)|Замещает двух строк для формата символ «%1» и «%2» в строке содержится в таблице строк.|  
|[AfxMessageBox](#afxmessagebox)|Отображает окно сообщения.|  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxextractsubstring"></a>  AfxExtractSubString  
 Это глобальная функция используется для извлечения подстроки из заданной исходной строки.  
  
```   
BOOL AFXAPI AfxExtractSubString (
    CString& rString,  
    LPCTSTR lpszFullString,  
    int iSubString,  
    TCHAR chSep  = '\n'); 
```  
  
### <a name="parameters"></a>Параметры  
 *rString*  
 -   Ссылка на [CString](../../atl-mfc-shared/using-cstring.md) объект, который будет получать отдельные подстроки.  
  
 *lpszFullString*  
 -   Строка, содержащая полный текст строки для извлечения из.  
  
 *iSubString*  
 -   Отсчитываемый от нуля индекс подстроки, которую требуется извлечь из *lpszFullString*.  
  
 *chSep*  
 -   Разделитель, который используется для разделения подстрок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если функция успешно извлечен подстроку по указанному индексу; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для извлечения нескольких подстрок из строки источника, если известных один символ отделяет каждой подстроке. Эта функция осуществляет поиск с начала *lpszFullString* параметр при каждом вызове.  
  
 Эта функция возвращает значение FALSE, если параметр *lpszFullString* имеет значение NULL или функция достигает конца *lpszFullString* без поиск *iSubString*+ 1 вхождения указанным знаком-разделителем. *RString* параметр не будет изменен исходное значение, если *lpszFullString* было установлено в значение NULL; в противном случае — *rString* параметра задано значение пустой строки, если не удалось извлечь подстроку по указанному индексу.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxformatstring1"></a>  AfxFormatString1  
 Замена строки, на который указывает *lpsz1* для любых экземпляров символов «%1» в ресурс строки шаблона, определенный *nIDS*.  
  
```  
void  AfxFormatString1(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1); 
```  
  
### <a name="parameters"></a>Параметры  
 *rString*  
 Ссылку на `CString` объект, который будет содержать результирующая строка после выполнения подстановки.  
  
 *nIDS*  
 Идентификатор ресурса строки шаблона, на котором выполняется замена.  
  
 *lpsz1*  
 Строка, которая заменит формат символов «%1» в строке шаблона.  
  
### <a name="remarks"></a>Примечания  
 Вновь сформированный строка хранится в *rString*. Например, если строка в таблице строк «Файла %1 не найден» и *lpsz1* равен «C:\MYFILE. TXT», затем *rString* будет содержать строку «файл C:\MYFILE. TXT не найден». Эта функция полезна для форматирования строк, отправляемых в окнах сообщений и других окнах.  
  
 Если символы форматирования «%1» более одного раза появляется в строке, будут выполняться несколько подстановок.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxformatstring2"></a>  AfxFormatString2  
 Замена строки, на который указывает *lpsz1* все экземпляры символов «%1» и строки, на который указывает *lpsz2* для любых экземпляров символов «%2» в ресурс строки шаблона определяется *nIDS*.  
  
```   
void AfxFormatString2(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1,  
    LPCTSTR lpsz2); 
```  
  
### <a name="parameters"></a>Параметры  
 *rString*  
 Ссылку на `CString` , содержащий результирующие строки после выполнения подстановки.  
  
 *nIDS*  
 Идентификатор строки таблицы строки шаблона, на котором выполняется замена.  
  
 *lpsz1*  
 Строка, которая заменит формат символов «%1» в строке шаблона.  
  
 *lpsz2*  
 Строка, которая заменит формат символов «%2» в строке шаблона.  
  
### <a name="remarks"></a>Примечания  
 Вновь сформированный строка хранится в *rString*. Например, если строка в таблице строк «Файла %1 не найден в каталоге %2» *lpsz1* указывает на «MYFILE. "TXT», и *lpsz2* указывает на «C:\MYDIR», затем *rString* будет содержать строку «файла MYFILE. TXT, не найден в каталоге C:\MYDIR»  
  
 Если формат символов «%1» или «%2» будут отображаться в строке несколько раз, будет выполнен несколько подстановок. Они не должны быть в числовом порядке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxmessagebox"></a>  AfxMessageBox  
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
 *lpszText*  
 Указывает на `CString` объект или символом null строку, содержащую сообщение, отображаемое в окне сообщения.  
  
 *nType*  
 Стиль окна сообщения. Применить любой из [стили окна сообщений](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) в поле.  
  
 *nIDHelp*  
 Идентификатор контекста справки для сообщения. 0 указывает, что будет использоваться контекст справки приложения по умолчанию.  
  
 *nIDPrompt*  
 Уникальный идентификатор, используемый для ссылки на строки в таблице строк.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если не хватает памяти для отображения окна сообщений. в противном случае возвращается одно из следующих значений:  
  
- Выбран вариант IDABORT Abort.  
  
- Отмена IDCANCEL был выбран.  
  
- Игнорировать IDIGNORE был выбран.  
  
- Выбран вариант IDNO нет.  
  
- Кнопка ОК IDOK был выбран.  
  
- Повторите IDRETRY был выбран.  
  
- Выбран IDYES кнопку Да.  
  
 Если окно сообщения содержит кнопку "Отмена", будет возвращено значение IDCANCEL, если нажата клавиша ESC или кнопку "Отмена". Если окно сообщения содержит нет кнопки "Отмена", нажав клавишу ESC не оказывает влияния.  
  
 Функции [AfxFormatString1](#afxformatstring1) и [AfxFormatString2](#afxformatstring2) можно использовать для форматирования текста, отображаемого в окне сообщения.  
  
### <a name="remarks"></a>Примечания  
 Первая форма перегруженные функции отображается строка текста, на который указывает *lpszText* в окне сообщения и использует *nIDHelp* для описания контекст справки. Контекст справки используется для перехода к соответствующие разделы справки, когда пользователь нажимает клавишу справки (обычно F1).  
  
 Вторая форма функции использует строковый ресурс с Идентификатором *nIDPrompt* для отображения сообщения в окне сообщения. Соответствующая страница справки находится с помощью значения *nIDHelp*. Если значение по умолчанию *nIDHelp* -используется (1), идентификатор строкового ресурса *nIDPrompt*, используется для контекста справки. Дополнительные сведения об определении контексты справки см. в разделе [Технические заметки 28](../../mfc/tn028-context-sensitive-help-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)
