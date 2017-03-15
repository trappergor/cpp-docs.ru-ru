---
title: "Класс CGopherLocator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherLocator
dev_langs:
- C++
helpviewer_keywords:
- gopher locator
- CGopherLocator class
- Internet, gopher searches
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c5c9b862714d046bc81a49dda27fd5fc062b9ba8
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherlocator-class"></a>Класс CGopherLocator
Получает средство «указатель» сервера gopher, определяет тип указателя и делает доступными для обнаружения [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены устарели, так как они не работают на платформе Windows XP, но они будут продолжать работать на более старых платформ.  
  
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
|[CGopherLocator::GetLocatorType](#getlocatortype)|Анализирует локатора gopher и определяет его атрибуты.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|Напрямую обращается к символов, сохраненных в `CGopherLocator` объект в виде строки в стиле C.|  
  
## <a name="remarks"></a>Примечания  
 Он может получать сведения с этого сервера приложения необходимо получить указатель на gopher-сервер. Получив указателя, он указателя следует рассматривать как непрозрачный маркер.  
  
 Каждый gopher указатель имеет атрибуты, определяющие тип файла или сервер найден. В разделе [GetLocatorType](#getlocatortype) список типов указателей gopher.  
  
 Приложение обычно использует указатель для вызовов [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) для получения конкретного набора данных.  
  
 Дополнительные сведения о том, как `CGopherLocator` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="a-namecgopherlocatora--cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a>CGopherLocator::CGopherLocator  
 Эта функция-член вызывается для создания `CGopherLocator` объекта.  
  
```  
CGopherLocator(const CGopherLocator& ref);
```  
  
### <a name="parameters"></a>Параметры  
 `ref`  
 Ссылку на константу `CGopherLocator` объекта.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CGopherLocator` напрямую. Вместо этого необходимо вызвать [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) создается и возвращается указатель на `CGopherLocator` объект.  
  
##  <a name="a-namegetlocatortypea--cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a>CGopherLocator::GetLocatorType  
 Вызовите эту функцию-член для получения типа указателя.  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *dwRef*  
 Ссылку на `DWORD` , принимающий тип указателя. В разделе **примечания** таблицу типы указателя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Ниже приведены возможные типы:  
  
|Значение|Значение|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|Текстовый файл ASCII.|  
|GOPHER_TYPE_DIRECTORY|Каталог дополнительных элементов Gopher.|  
|GOPHER_TYPE_CSO|Сервер CSO телефонной книги.|  
|GOPHER_TYPE_ERROR|Указывает на ошибку.|  
|GOPHER_TYPE_MAC_BINHEX|Файл Macintosh в формате BINHEX.|  
|GOPHER_TYPE_DOS_ARCHIVE|Файл архива DOS.|  
|GOPHER_TYPE_UNIX_UUENCODED|Файл кодировке UUENCODE.|  
|GOPHER_TYPE_INDEX_SERVER|На сервере индекса.|  
|GOPHER_TYPE_TELNET|Сервер Telnet.|  
|GOPHER_TYPE_BINARY|Двоичный файл.|  
|GOPHER_TYPE_REDUNDANT|Дублирование сервера. Сведения, содержащиеся в совпадает с основного сервера. Сервер-источник является последней записи каталога, который не имеет тип GOPHER_TYPE_REDUNDANT.|  
|GOPHER_TYPE_TN3270|Сервер TN3270.|  
|GOPHER_TYPE_GIF|Файл GIF графики.|  
|GOPHER_TYPE_IMAGE|Файл изображения.|  
|GOPHER_TYPE_BITMAP|Файл точечного рисунка.|  
|GOPHER_TYPE_MOVIE|Файл фильма.|  
|GOPHER_TYPE_SOUND|Звуковой файл.|  
|GOPHER_TYPE_HTML|Документ HTML.|  
|GOPHER_TYPE_PDF|PDF-файла.|  
|GOPHER_TYPE_CALENDAR|Файл календаря.|  
|GOPHER_TYPE_INLINE|Встроенный файл.|  
|GOPHER_TYPE_UNKNOWN|Тип элемента неизвестен.|  
|GOPHER_TYPE_ASK|Попросите + элемента.|  
|GOPHER_TYPE_GOPHER_PLUS|Элемента Gopher +.|  
  
##  <a name="a-nameoperatorlpctstra--cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a>CGopherLocator::operator LPCTSTR  
 Этот оператор полезных приведения предоставляет эффективный способ доступа к нулем строка C, содержащихся в `CGopherLocator` объекта.  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель символа строки данных.  
  
### <a name="remarks"></a>Примечания  
 Символы не копируются; возвращается только указатель.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)

