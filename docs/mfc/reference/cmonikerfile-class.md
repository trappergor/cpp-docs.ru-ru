---
title: "Класс CMonikerFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile class
- monikers, MFC
- IMoniker interface, binding
- IMoniker interface
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0f348328a4be4b934e00acdb43ba47fa919bac75
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="cmonikerfile-class"></a>Класс CMonikerFile
Представляет поток данных ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) с именем [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Создает объект `CMonikerFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Отсоединяет и освобождает поток и освобождает моникер.|  
|[CMonikerFile::Detach](#detach)|Отсоединяет `IMoniker` из этого `CMonikerFile` объекта.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Возвращает текущий моникер.|  
|[CMonikerFile::Open](#open)|Открывает указанный файл, чтобы получить поток.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Получает контекст привязки, или создает контекст привязки по умолчанию.|  
  
## <a name="remarks"></a>Примечания  
 Моникер сведения как путь к файлу. Если имеется указатель на объект моникера `IMoniker` интерфейс, без необходимости любую конкретную информацию о расположении файла фактически можно получить доступ к определенного файла.  
  
 Производное от `COleStreamFile`, `CMonikerFile` принимает моникер или строковое представление, его можно преобразовать в моникер и привязывает к потоку, для которого моникер — это имя. Кроме того, можно затем чтения и записи в поток. Реальные назначение `CMonikerFile` — для обеспечения простого доступа к `IStream`s с именем `IMoniker`s, чтобы не требовалось выполнить привязку к потоку самостоятельно, еще нет `CFile` функциональные возможности в поток.  
  
 `CMonikerFile`не может использоваться для привязки к ничего, кроме потока. Если вы хотите привязать к хранилища или объекта, необходимо использовать `IMoniker` интерфейс непосредственно.  
  
 Дополнительные сведения о потоках и моникеров. в разделе [COleStreamFile](../../mfc/reference/colestreamfile-class.md) в *Справочник по библиотеке MFC* и [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) и [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="close"></a>CMonikerFile::Close  
 Вызывайте эту функцию для выделения и освобождения потока и чтобы освободить моникер.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Может быть вызван потоки неоткрытый или уже закрыт.  
  
##  <a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 Создает объект `CMonikerFile`.  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 Эта функция вызывается для создания контекста привязки по умолчанию.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Параметры  
 `pError`  
 Указатель на исключение файлов. В случае ошибки он будет присвоено причину.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на контекст привязки [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) для привязки с, если успешно; в противном случае **NULL**. Если экземпляр был открыт с `IBindHost` интерфейс, контекст привязки извлекается из `IBindHost`. При наличии не `IBindHost` или в интерфейсе не возвращает контекста привязки, создается контекста привязки. Описание [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) интерфейса см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Контекст привязки — объект, который хранит сведения о выполнении операции привязки моникера определенного. Можно переопределить эту функцию для предоставления контекста пользовательской привязки.  
  
##  <a name="detach"></a>CMonikerFile::Detach  
 Вызывайте эту функцию для закрытия потока.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pError`  
 Указатель на исключение файлов. В случае ошибки он будет присвоено причину.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="getmoniker"></a>CMonikerFile::GetMoniker  
 Эта функция вызывается для получения указателя на текущий моникер.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий интерфейс моникер ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Примечания  
 Так как `CMonikerFile` не является интерфейсом, возвращенный указатель не увеличивает счетчик ссылок (через [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), и моникер освобождается при `CMonikerFile` объект освобождается. Если требуется удерживать моникер или освободите его необходимо `AddRef` его.  
  
##  <a name="open"></a>CMonikerFile::Open  
 Вызовите эту функцию-член для открытия файла или моникер объекта.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszURL`  
 URL-адрес или имя файла для открытия.  
  
 `pError`  
 Указатель на исключение файлов. В случае ошибки он будет присвоено причину.  
  
 `pMoniker`  
 Указатель на интерфейс моникер `IMoniker` использоваться для получения потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `lpszURL` Параметр нельзя использовать на компьютерах Macintosh. Только `pMoniker` форму **откройте** можно использовать на компьютерах Macintosh.  
  
 Можно использовать URL-адрес или имя файла для `lpszURL` параметра. Пример:  
  
 [!code-cpp[NVC_MFCWinInet #6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 - или  
  
 [!code-cpp[NVC_MFCWinInet #7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс COleStreamFile](../../mfc/reference/colestreamfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

