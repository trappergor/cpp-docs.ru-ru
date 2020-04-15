---
title: Форматирование CString и отображение окна сообщения
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
ms.openlocfilehash: d30d26ecf0e72ee33affe3df5b88c438ff83bb6b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365997"
---
# <a name="cstring-formatting-and-message-box-display"></a>Форматирование CString и отображение окна сообщения

Для формата и разбора `CString` объектов предусмотрен ряд функций. Вы можете использовать эти функции всякий раз, когда вам нужно манипулировать `CString` объектами, но они особенно полезны для форматирования строк, которые будут отображаться в тексте коробки сообщений.

Эта группа функций также включает в себя глобальную рутину для отображения ящика сообщений.

### <a name="cstring-functions"></a>Функции CString

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|Извлекает подстроки, отделенные одним символом от заданной строки источника.|
|[AfxFormatString1](#afxformatstring1)|Заменяет заданную строку для символов формата "%1" в строке, содержащейся в строке строки.|
|[AfxFormatString2](#afxformatstring2)|Заменяет две строки для символов формата "%1" и "%2" в строке, содержащейся в таблице строки.|
|[AfxMessageBox](#afxmessagebox)|Отображает окно сообщения.|

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxextractsubstring"></a><a name="afxextractsubstring"></a>AfxExtractSubString

Эта глобальная функция может быть использована для извлечения подстроки из данной строки источника.

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>Параметры

*rString*<br/>
Ссылка на объект [CString,](../../atl-mfc-shared/using-cstring.md) который получит отдельный подстроку.

*lpszFullString*<br/>
Строка, содержащая полный текст строки для извлечения из.

*iSubString*<br/>
Нулевой индекс подстроки для извлечения из *lpszFullString*.

*chSep*<br/>
Символ сепаратора используется для разгранижения подстроек.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если функция успешно извлекла подстроку в при условии индекса; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Эта функция полезна для извлечения нескольких подстроек из строки исходного кода, когда известный один символ отделяет каждую подстроку. Эта функция выполняет поиск с самого начала параметра *lpszFullString* каждый раз, когда она вызывается.

Эта функция вернет FALSE, если *lpszFullString* установлен в NULL или функция достигнет конца *lpszFullString,* не найдя *возникновения iSubString*No1 указанного символа сепаратора. Параметр *rString* не будет изменен с исходного значения, если *lpszFullString* был установлен на NULL; в противном случае параметр *rString* устанавливается на пустую строку, если подстрока не может быть извлечена для указанного индекса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxformatstring1"></a><a name="afxformatstring1"></a>AfxFormatString1

Заменяет строку, на которую указывает *lpsz1* для любых экземпляров символов "%1" в ресурсе строки шаблона, идентифицированном *nIDS.*

```
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>Параметры

*rString*<br/>
Ссылка на `CString` объект, который будет содержать резукторную строку после выполнения замены.

*nIDS*<br/>
Идентификатор ресурса строки шаблона, на которой будет выполняться замена.

*lpsz1*<br/>
Строка, которая заменит символы формата "%1" в строке шаблона.

### <a name="remarks"></a>Remarks

Вновь сформированная строка хранится в *rString*. Например, если строка в строке таблицы "Файл %1 не найден", а *lpsz1* равен "C:'MYFILE. TXT", затем *rString* будет содержать строку "File C:'MYFILE. TXT не найдено». Эта функция полезна для форматирования строк, отправляемых в почтовые ящики и другие окна.

Если символы формата "%1" появляются в строке более одного раза, будет произведено несколько замен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxformatstring2"></a><a name="afxformatstring2"></a>AfxFormatString2

Заменяет строку, указанную *lpsz1* для любых экземпляров символов "%1", и строку, указанную *lpsz2* для любых экземпляров символов "%2", в ресурсе строки шаблона, идентифицированного *nIDS.*

```
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>Параметры

*rString*<br/>
Ссылка на `CString` строку, которая будет содержать резукторную строку после выполнения замены.

*nIDS*<br/>
Идентификатор строки таблицы строки шаблона, на котором будет выполняться замена.

*lpsz1*<br/>
Строка, которая заменит символы формата "%1" в строке шаблона.

*lpsz2*<br/>
Строка, которая заменит символы формата "%2" в строке шаблона.

### <a name="remarks"></a>Remarks

Вновь сформированная строка хранится в *rString*. Например, если строка в строке таблицы "Файл %1 не найден в каталоге %2", *lpsz1* указывает на "MYFILE. TXT", и *lpsz2* указывает на "C: 'MYDIR", то *rString* будет содержать строку "File MYFILE. TXT не найден в каталоге C: »MYDIR"

Если символы формата «%1» или «%2» появляются в строке более одного раза, будет произведено несколько замен. Они не должны быть в численном порядке.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxmessagebox"></a><a name="afxmessagebox"></a>AfxMessageBox

Отображает поле сообщения на экране.

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

*lpszText*<br/>
Очки `CString` на объект или нулевую строку, содержащую сообщение, отображаемый в поле сообщения.

*nType*<br/>
Стиль коробки сообщений. Примените к коробке любой [из стилей почтового ящика.](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)

*nIDHelp*<br/>
Идентификатор контекста справки для сообщения; 0 указывает на то, что будет использоваться контекст справки по умолчанию приложения.

*nIDPrompt*<br/>
Уникальный идентификатор, используемый для ссылки на строку в таблице строки.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если не хватает памяти для отображения ящика сообщений; в противном случае возвращается одно из следующих значений:

- Выбрана кнопка IDABORT Abort.

- Выбрана кнопка IDCANCEL Отмена.

- Выбрана кнопка IDIGNORE «Игнорировать».

- Выбрана кнопка IDNO No.

- IDOK Кнопка OK была выбрана.

- Выбрана кнопка IDRETRY Retry.

- IdYES Была выбрана кнопка Yes.

Если в поле сообщения есть кнопка «Отмена», значение IDCANCEL будет возвращено при нажатии ключа ESC или выбранной кнопке «Отмена». Если в поле сообщения нет кнопки Отмена, нажатие клавиши ESC не имеет никакого эффекта.

Функции [AfxFormatString1](#afxformatstring1) и [AfxFormatString2](#afxformatstring2) могут быть полезны при форматировании текста, который отображается в поле сообщений.

### <a name="remarks"></a>Remarks

Первая форма этой перегруженной функции отображает текстовую строку, на которую указывает *lpszText* в поле сообщений, и использует *nIDHelp* для описания контекста справки. Контекст справки используется для перехода к связанной теме справки при нажатии на клавишу справки (обычно F1).

Вторая форма функции использует ресурс строки с ID *nIDPrompt* для отображения сообщения в поле сообщения. Связанная страница справки находится через значение *nIDHelp.* Если используется значение *nIDHelp* по умолчанию (-1), идентификатор ресурса *строки, nIDPrompt,* используется для контекста справки. Для получения дополнительной информации об определении контекстов справки [см.](../../mfc/tn028-context-sensitive-help-support.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)
