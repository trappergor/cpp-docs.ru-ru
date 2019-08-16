---
title: Класс Кгоферлокатор
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: 9ce95a712af6502bff2a2502582a7fa843bf9653
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506162"
---
# <a name="cgopherlocator-class"></a>Класс Кгоферлокатор

Получает Gopher "Локатор" от сервера gopher, определяет тип указателя и делает указатель доступным для [кгоферфилефинд](../../mfc/reference/cgopherfilefind-class.md).

> [!NOTE]
>  Классы `CGopherConnection` `CGopherFile` ,`CGopherLocator` , и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они продолжат работать на более ранних `CGopherFileFind`платформах.

## <a name="syntax"></a>Синтаксис

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кгоферлокатор:: Кгоферлокатор](#cgopherlocator)|Создает объект `CGopherLocator`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кгоферлокатор:: Жетлокатортипе](#getlocatortype)|Анализирует локатор Gopher и определяет его атрибуты.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Кгоферлокатор:: operator LPCTSTR](#operator_lpctstr)|Прямой доступ к символам, хранящимся в `CGopherLocator` объекте, в виде строки в стиле C.|

## <a name="remarks"></a>Примечания

Приложение должно получить локатор сервера gopher, прежде чем он сможет получить сведения с этого сервера. После того, как он содержит указатель, он должен обрабатывать указатель как непрозрачный токен.

Каждый локатор Gopher имеет атрибуты, которые определяют тип найденного файла или сервера. Список типов локаторов Gopher см. в разделе [жетлокатортипе](#getlocatortype) .

Приложение обычно использует локатор для вызовов [кгоферфилефинд:: финдфиле](../../mfc/reference/cgopherfilefind-class.md#findfile) для получения определенного фрагмента информации.

Дополнительные сведения о `CGopherLocator` работе с другими классами Интернета MFC см. в статье Интернет – [программирование с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Требования

**Заголовок:** афксинет. h

##  <a name="cgopherlocator"></a>Кгоферлокатор:: Кгоферлокатор

Эта функция-член вызывается для создания `CGopherLocator` объекта.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Параметры

*ref*<br/>
Ссылка на постоянный `CGopherLocator` объект.

### <a name="remarks"></a>Примечания

Вы никогда не создаете `CGopherLocator` объект напрямую. Вместо этого вызовите метод [кгоферконнектион:: CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) , чтобы создать и вернуть указатель `CGopherLocator` на объект.

##  <a name="getlocatortype"></a>Кгоферлокатор:: Жетлокатортипе

Вызовите эту функцию члена, чтобы получить тип указателя.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Параметры

*двреф*<br/>
Ссылка на DWORD, который получит тип указателя. См. раздел **Примечания** для таблицы типов указателей.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, можно вызвать функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы определить причину ошибки.

### <a name="remarks"></a>Примечания

Возможны следующие типы:

|Значение|Значение|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|Текстовый файл в формате ASCII.|
|GOPHER_TYPE_DIRECTORY|Каталог дополнительных элементов gopher.|
|GOPHER_TYPE_CSO|Сервер телефонной книги CSO.|
|GOPHER_TYPE_ERROR|Указывает на состояние ошибки.|
|GOPHER_TYPE_MAC_BINHEX|Файл Macintosh в формате BINHEX.|
|GOPHER_TYPE_DOS_ARCHIVE|Файл архива DOS.|
|GOPHER_TYPE_UNIX_UUENCODED|Файл УУЕНКОДЕД.|
|GOPHER_TYPE_INDEX_SERVER|Сервер индекса.|
|GOPHER_TYPE_TELNET|Сервер Telnet.|
|GOPHER_TYPE_BINARY|Двоичный файл.|
|GOPHER_TYPE_REDUNDANT|Дублирующийся сервер. Информация, содержащаяся в, является дубликатом сервера-источника. Сервер-источник — это последняя запись каталога, которая не имеет типа GOPHER_TYPE_REDUNDANT.|
|GOPHER_TYPE_TN3270|Сервер TN3270.|
|GOPHER_TYPE_GIF|Графический файл GIF.|
|GOPHER_TYPE_IMAGE|Файл изображения.|
|GOPHER_TYPE_BITMAP|Файл точечного рисунка.|
|GOPHER_TYPE_MOVIE|Файл фильма.|
|GOPHER_TYPE_SOUND|Звуковой файл.|
|GOPHER_TYPE_HTML|Документ HTML.|
|GOPHER_TYPE_PDF|PDF-файл.|
|GOPHER_TYPE_CALENDAR|Файл календаря.|
|GOPHER_TYPE_INLINE|Встроенный файл.|
|GOPHER_TYPE_UNKNOWN|Неизвестный тип элемента.|
|GOPHER_TYPE_ASK|Запрос и элемент.|
|GOPHER_TYPE_GOPHER_PLUS|Элемент Gopher +.|

##  <a name="operator_lpctstr"></a>Кгоферлокатор:: operator LPCTSTR

Этот полезный оператор приведения предоставляет эффективный метод доступа к строке C, завершающейся нулем, содержащемуся в `CGopherLocator` объекте.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символа на данные строки.

### <a name="remarks"></a>Примечания

Символы не копируются; возвращается только указатель.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)
