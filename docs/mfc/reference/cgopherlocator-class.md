---
title: Класс CGopherLocator | Документы Microsoft
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
ms.openlocfilehash: 377708108f96a42d23dcf3aa5e8214d7bf9ffe5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cgopherlocator-class"></a>Класс CGopherLocator
Получает средство «указатель» с сервера gopher, определяет тип средства поиска и делает средство поиска доступным для [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они будут продолжать работать на более старых платформ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CGopherLocator : public CObject  
```  
  
## <a name="members"></a>Члены  
  
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
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|Прямой доступ к символов, сохраненных в `CGopherLocator` объект в виде строки в стиле C.|  
  
## <a name="remarks"></a>Примечания  
 Приложению необходимо получить указатель на сервере gopher получать сведения с этого сервера. Получив локатора, он локаторе следует рассматривать как непрозрачный маркер.  
  
 Каждый gopher указатель имеет атрибуты, определяющие тип файла или сервер найден. В разделе [GetLocatorType](#getlocatortype) список типов указателей gopher.  
  
 Приложение обычно использует локатор для вызовов [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) для получения конкретные сведения.  
  
 Дополнительные сведения о том, как `CGopherLocator` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
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
 `ref`  
 Ссылка на константу `CGopherLocator` объекта.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавайте `CGopherLocator` объекта напрямую. Вместо этого необходимо вызвать [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) создается и возвращается указатель `CGopherLocator` объекта.  
  
##  <a name="getlocatortype"></a>  CGopherLocator::GetLocatorType  
 Вызовите эту функцию-член для получения типа указателя.  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *dwRef*  
 Ссылку на `DWORD` , принимающий тип указателя. В разделе **примечания** для таблицы типов указателя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Ниже приведены возможные типы:  
  
|Значение|Смысл|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|Текстовый файл.|  
|GOPHER_TYPE_DIRECTORY|Каталог дополнительные элементы Gopher.|  
|GOPHER_TYPE_CSO|Сервер CSO телефонной книги.|  
|GOPHER_TYPE_ERROR|Указывает на ошибку.|  
|GOPHER_TYPE_MAC_BINHEX|Файл в формате BINHEX Macintosh.|  
|GOPHER_TYPE_DOS_ARCHIVE|Файл архива DOS.|  
|GOPHER_TYPE_UNIX_UUENCODED|В файл в кодировке UUENCODE.|  
|GOPHER_TYPE_INDEX_SERVER|На сервере индекса.|  
|GOPHER_TYPE_TELNET|Telnet-сервер.|  
|GOPHER_TYPE_BINARY|Двоичный файл.|  
|GOPHER_TYPE_REDUNDANT|Повторяющийся сервер. Сведения, содержащиеся в является дубликатом сервера-источника. Сервер-источник является последней записи каталога, но не имеют тип GOPHER_TYPE_REDUNDANT.|  
|GOPHER_TYPE_TN3270|Сервер TN3270.|  
|GOPHER_TYPE_GIF|Графики GIF-файла.|  
|GOPHER_TYPE_IMAGE|Файл изображения.|  
|GOPHER_TYPE_BITMAP|Файл точечного рисунка.|  
|GOPHER_TYPE_MOVIE|Файл фильма.|  
|GOPHER_TYPE_SOUND|Звуковой файл.|  
|GOPHER_TYPE_HTML|Документ HTML.|  
|GOPHER_TYPE_PDF|PDF-файл.|  
|GOPHER_TYPE_CALENDAR|Файл календаря.|  
|GOPHER_TYPE_INLINE|Подставляемый файл.|  
|GOPHER_TYPE_UNKNOWN|Тип элемента неизвестен.|  
|GOPHER_TYPE_ASK|Попросите + элемент.|  
|GOPHER_TYPE_GOPHER_PLUS|Элемент Gopher +.|  
  
##  <a name="operator_lpctstr"></a>  CGopherLocator::operator LPCTSTR  
 Этот оператор приведения полезные предоставляет эффективный метод для доступа к строке C нулем, содержащихся в `CGopherLocator` объекта.  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Символ указатель строки данных.  
  
### <a name="remarks"></a>Примечания  
 Никакие символы копируются; возвращается только указатель.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)
