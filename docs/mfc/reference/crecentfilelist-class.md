---
title: Класс CRecentFileList | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
dev_langs:
- C++
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 680c09a402f5143169021403305805dc141ff5a9
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853099"
---
# <a name="crecentfilelist-class"></a>Класс CRecentFileList
Поддерживает элемент управления последнего использовавшегося списка файлов (MRU).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Создает объект `CRecentFileList`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|Добавляет файл в список последних Выбиравшихся файлов.|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|Предоставляет отображаемое имя для отображения меню файла MRU.|  
|[CRecentFileList::GetSize](#getsize)|Получает число файлов в списке последних Выбиравшихся файлов.|  
|[CRecentFileList::ReadList](#readlist)|Считывает список последних Использованных файлов из реестра или. INI-файл.|  
|[CRecentFileList::Remove](#remove)|Удаляет файл из списка последних Использованных файлов.|  
|[CRecentFileList::UpdateMenu](#updatemenu)|Обновляет отображение меню список последних Выбиравшихся файлов.|  
|[CRecentFileList::WriteList](#writelist)|Записывает список последних Использованных файлов из реестра или. INI-файл.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[[CRecentFileList::operator]](#operator_at)|Возвращает `CString` объекта в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 Файлы можно добавить или удалить из списка последних Использованных файлов, список файлов может быть чтения или записи в реестр или. Можно обновить INI-файл и меню, отображение в списке последних Выбиравшихся файлов.  
  
 Дополнительные сведения о последних Использованных элементов меню см. в разделе  
  
-   Статье базы знаний Q243751: Практическое руководство: Добавление обработчики команд для последних Использованных элементов меню в приложении MFC  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CRecentFileList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="add"></a>  CRecentFileList::Add  
 Добавляет файл в списке недавно использованных файлов (MRU).  
  
```  
virtual void Add(LPCTSTR lpszPathName);

 
virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

 
void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

 
void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

 
void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPathName*  
 Указывает путь для добавления в список.  
  
 *lpszAppID*  
 Указывает идентификатор модели пользователя приложения для приложения.  
  
 *pItem*  
 Задает указатель на элемент оболочки для добавления в список.  
  
 *инструмент pLink*  
 Задает указатель на ссылку оболочки для добавления в список.  
  
 *pidl*  
 Указывает списка ИДЕНТИФИКАТОРОВ для элемента оболочки, который должен быть добавлен в папку последние документы.  
  
### <a name="remarks"></a>Примечания  
 Имя файла добавляется в начало списка последних выбиравшихся файлов. Если имя файла уже существует в списке последних выбиравшихся файлов, он перемещается в начало.  
  
##  <a name="crecentfilelist"></a>  CRecentFileList::CRecentFileList  
 Создает объект `CRecentFileList`.  
  
```  
CRecentFileList(
    UINT nStart,  
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntryFormat,  
    int nSize,  
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```  
  
### <a name="parameters"></a>Параметры  
 *nвремя запуска*  
 Смещение для нумерации при отображении меню списка файлов (самые последние использовавшиеся) MRU.  
  
 *lpszSection*  
 Указывает имя раздела реестра или приложения. INI-файл, где список последних Использованных файлов чтения или записи.  
  
 *lpszEntryFormat*  
 Указывает строку формата, используемый для имен записей, хранимых в реестре или приложения. INI-файл.  
  
 *nSize*  
 Максимальное число файлов в списке последних Выбиравшихся файлов.  
  
 *nMaxDispLen*  
 Максимальная длина в символах, доступные для отображения меню имя файла в списке последних Выбиравшихся файлов.  
  
### <a name="remarks"></a>Примечания  
 Строка формата, на который указывает *lpszEntryFormat* должен содержать «%d», которая будет использоваться для замены индекс каждого элемента в списке последних выбиравшихся файлов. Например, если строка формата является `"file%d"` затем записи будет называться `file0`, `file1`, и т. д.  
  
##  <a name="getdisplayname"></a>  CRecentFileList::GetDisplayName  
 Получает отображаемое имя для файла в списке последних Выбиравшихся файлов для использования при отображении меню списке MRU.  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *strName*  
 Полный путь к файлу, имя которого будет отображаться в списке меню последних Использованных файлов.  
  
 *nIndex*  
 Отсчитываемый от нуля индекс файла в списке последних Выбиравшихся файлов.  
  
 *lpszCurDir*  
 Строка, содержащая текущий каталог.  
  
 *nCurDir*  
 Длина строки текущего каталога.  
  
 *bAtLeastName*  
 Если не равен нулю, указывает, что должно возвращаться базовое имя файла, даже если оно превышает максимальное отображаемое (передан в качестве *nMaxDispLen* параметр `CRecentFileList` конструктора).  
  
### <a name="return-value"></a>Возвращаемое значение  
 **FALSE** имеется ли имя файла по указанному индексу в списке недавно использованных файлов (MRU).  
  
### <a name="remarks"></a>Примечания  
 Если файл находится в текущем каталоге, функция оставляет directory скрыть. Слишком длинное имя файла, каталога и расширение вырезаются. Если имя файла по-прежнему слишком длинный, отображаемое имя имеет значение на пустую строку, если не *bAtLeastName* имеет ненулевое значение.  
  
##  <a name="getsize"></a>  CRecentFileList::GetSize  
 Получает число файлов в списке последних Выбиравшихся файлов.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число файлов в текущем самые последние использовавшиеся список файлов (MRU).  
  
##  <a name="operator_at"></a>  [CRecentFileList::operator]  
 Перегруженный нижнего индекса (`[]`) оператор возвращает одиночный `CString` определяемое отсчитываемый от нуля индекс в *nIndex*.  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Отсчитываемый от нуля индекс `CString` в наборе `CString`s.  
  
##  <a name="readlist"></a>  CRecentFileList::ReadList  
 Считывает недавно использовавшиеся список файлов (MRU) в реестре или приложения. INI-файл.  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>  CRecentFileList::Remove  
 Удаляет файл из списка последних Использованных файлов.  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Отсчитываемый от нуля индекс файла, удаляемого из списка последних использованных файлов (MRU).  
  
##  <a name="updatemenu"></a>  CRecentFileList::UpdateMenu  
 Обновляет отображение меню список последних Выбиравшихся файлов.  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 *pCmdUI*  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объект для меню списка недавно использованных файлов (MRU).  
  
##  <a name="writelist"></a>  CRecentFileList::WriteList  
 Записывает последние использовавшиеся список файлов (MRU) в реестре или приложения. INI-файл.  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



