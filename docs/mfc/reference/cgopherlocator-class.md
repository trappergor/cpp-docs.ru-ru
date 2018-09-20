---
title: Класс CGopherLocator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
dev_langs:
- C++
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d9309917fe89abbf3679060898861e1c698d660
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445845"
---
# <a name="cgopherlocator-class"></a>Класс CGopherLocator

Получает средство «указатель» с сервера gopher, определяет тип и делает средство поиска доступным для [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).

> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они будут продолжать работать на более ранние платформы.

## <a name="syntax"></a>Синтаксис

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Создает объект `CGopherLocator`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CGopherLocator::GetLocatorType](#getlocatortype)|Выполняет синтаксический анализ локатора gopher и определяет его атрибуты.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|Напрямую обращается к символов, сохраненных в `CGopherLocator` объект в виде строки C-стиля.|

## <a name="remarks"></a>Примечания

Приложение необходимо получить указатель на сервер gopher получать сведения с этого сервера. После получения указателя, он должен обрабатывать указателя как маркер является непрозрачным.

Каждый gopher указатель имеет атрибуты, которые определяют тип файла или сервер найден. См. в разделе [GetLocatorType](#getlocatortype) список типов указателей gopher.

Приложение обычно использует средство поиска для вызовов [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) для получения конкретного набора сведений.

Дополнительные сведения о том, как `CGopherLocator` работает с другими классами MFC Интернет, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="cgopherlocator"></a>  CGopherLocator::CGopherLocator

Эта функция-член вызывается для создания `CGopherLocator` объекта.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Параметры

*ref*<br/>
Ссылку на константу `CGopherLocator` объекта.

### <a name="remarks"></a>Примечания

Никогда не создаст `CGopherLocator` объекта напрямую. Вместо этого необходимо вызвать [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) создается и возвращается указатель на `CGopherLocator` объект.

##  <a name="getlocatortype"></a>  CGopherLocator::GetLocatorType

Вызов этой функции-члена для получения типа указателя.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Параметры

*dwRef*<br/>
Ссылка на значение типа DWORD, который будет получать тип указателя. См. в разделе **"Примечания"** таблицу типы локаторов.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

Ниже приведены возможные типы:

|Значение|Значение|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|Текстовый файл ASCII.|
|GOPHER_TYPE_DIRECTORY|Каталог дополнительных элементов Gopher.|
|GOPHER_TYPE_CSO|Сервер службы телефонной книги.|
|GOPHER_TYPE_ERROR|Указывает на ошибку.|
|GOPHER_TYPE_MAC_BINHEX|Файл Macintosh в формате BINHEX.|
|GOPHER_TYPE_DOS_ARCHIVE|В файл архива DOS.|
|GOPHER_TYPE_UNIX_UUENCODED|Файл кодировке UUENCODE.|
|GOPHER_TYPE_INDEX_SERVER|Сервер индекса.|
|GOPHER_TYPE_TELNET|Telnet-сервер.|
|GOPHER_TYPE_BINARY|Двоичный файл.|
|GOPHER_TYPE_REDUNDANT|Повторяющийся сервер. Сведения, содержащиеся в является дубликатом сервера-источника. Сервер-источник — последней записи каталога, но не имеют тип GOPHER_TYPE_REDUNDANT.|
|GOPHER_TYPE_TN3270|Сервер TN3270.|
|GOPHER_TYPE_GIF|Файл GIF графики.|
|GOPHER_TYPE_IMAGE|Файл изображения.|
|GOPHER_TYPE_BITMAP|Файл точечного рисунка.|
|GOPHER_TYPE_MOVIE|Файл фильма.|
|GOPHER_TYPE_SOUND|Звуковой файл.|
|GOPHER_TYPE_HTML|Документ HTML.|
|GOPHER_TYPE_PDF|PDF-файла.|
|GOPHER_TYPE_CALENDAR|Файл календаря.|
|GOPHER_TYPE_INLINE|Встроенного файла.|
|GOPHER_TYPE_UNKNOWN|Тип элемента неизвестен.|
|GOPHER_TYPE_ASK|Ask + элемент.|
|GOPHER_TYPE_GOPHER_PLUS|Элемент Gopher +.|

##  <a name="operator_lpctstr"></a>  CGopherLocator::operator LPCTSTR

Этот оператор полезных приведения предоставляет эффективный способ доступа к заканчивающуюся нулем строку C, содержащихся в `CGopherLocator` объекта.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Возвращаемое значение

Символ указатель на строку данных.

### <a name="remarks"></a>Примечания

Никакие символы не копируются; возвращается только указатель.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)
