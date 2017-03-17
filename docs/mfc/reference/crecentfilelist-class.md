---
title: "Класс CRecentFileList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- files [C++], most recently used
- MRU files
- CRecentFileList class
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
caps.latest.revision: 19
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
ms.openlocfilehash: 5d18daee2e4d809c750ae4654d731888df1db39e
ms.lasthandoff: 02/24/2017

---
# <a name="crecentfilelist-class"></a>Класс CRecentFileList
Поддерживает элемент управления последнего использовавшегося списка файлов (MRU).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Создает объект `CRecentFileList`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|Добавляет файл в список последних Использованных файлов.|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|Содержит отображаемое имя для отображения меню MRU filename.|  
|[CRecentFileList::GetSize](#getsize)|Получает число файлов в списке наиболее часто Используемых файлов.|  
|[CRecentFileList::ReadList](#readlist)|Считывает список последних Использованных файлов из реестра или. INI-файл.|  
|[CRecentFileList::Remove](#remove)|Удаляет файл из списка наиболее часто Используемых файлов.|  
|[CRecentFileList::UpdateMenu](#updatemenu)|Обновляет отображение меню списка Использованных файлов.|  
|[CRecentFileList::WriteList](#writelist)|Выводит список последних Использованных файлов из реестра или. INI-файл.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CRecentFileList::operator]](#operator_at)|Возвращает `CString` объект в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 Файлы могут быть добавляется или удаляется из списка последних Использованных файлов, список файлов для чтения и записи в реестр или. Можно обновить INI-файл и меню, отображение списка последних Использованных файлов.  
  
 Дополнительные сведения о последних Использованных элементов меню см.  
  
-   Статья базы знаний Q243751: Практическое руководство: добавление обработчиков команд для наиболее часто Используемых элементов меню в приложении MFC  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CRecentFileList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="add"></a>CRecentFileList::Add  
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
 `lpszPathName`  
 Указывает путь для добавления в список.  
  
 `lpszAppID`  
 Задает идентификатор модели приложения пользователя для приложения.  
  
 `pItem`  
 Задает указатель на элемент оболочки для добавления в список.  
  
 `pLink`  
 Задает указатель ссылка на оболочку для добавления в список.  
  
 `pidl`  
 Указывает СПИСОК_ИДЕНТИФИКАТОРОВ оболочки элемента, который должен быть добавлен в папку Недавние документы.  
  
### <a name="remarks"></a>Примечания  
 Имя файла будет добавлено в начало списка. Если имя файла уже существует в данном списке, перемещается в начало.  
  
##  <a name="crecentfilelist"></a>CRecentFileList::CRecentFileList  
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
 `nStart`  
 Смещение для нумерации в меню отображать список файлов MRU (самые последние использовавшиеся).  
  
 `lpszSection`  
 Указывает имя раздела реестра или приложения. INI-файл, где список последних Использованных файлов чтение или запись.  
  
 `lpszEntryFormat`  
 Указывает строку формата, используемый для имен записей, хранящихся в реестре или приложения. INI-файл.  
  
 `nSize`  
 Максимальное число файлов в списке наиболее часто Используемых файлов.  
  
 `nMaxDispLen`  
 Максимальная длина в символах для отображения меню имени файла в списке наиболее часто Используемых файлов.  
  
### <a name="remarks"></a>Примечания  
 Строка формата, на который указывает `lpszEntryFormat` должен содержать «%d», которая будет использоваться для замены индекс каждого элемента MRU. Например, если строка формата является `"file%d"` затем записи будет называться `file0`, `file1`и так далее.  
  
##  <a name="getdisplayname"></a>CRecentFileList::GetDisplayName  
 Получает отображаемое имя для файла в списке последних Использованных файлов для использования при отображении меню списка.  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strName`  
 Полный путь к файлу, имя которого будет отображаться в меню список последних Использованных файлов.  
  
 `nIndex`  
 Отсчитываемый от нуля индекс файла в список последних Использованных файлов.  
  
 *lpszCurDir*  
 Строка, содержащая текущий каталог.  
  
 *nCurDir*  
 Длина строки текущего каталога.  
  
 `bAtLeastName`  
 Если значение ненулевое, указывает, что должны быть возвращены базовое имя файла, даже если она превышает максимальное отображаемая длина (передается в качестве `nMaxDispLen` параметр `CRecentFileList` конструктора).  
  
### <a name="return-value"></a>Возвращаемое значение  
 **FALSE** есть имя файла по указанному индексу в списке недавно использованных файлов (MRU).  
  
### <a name="remarks"></a>Примечания  
 Если файл находится в текущем каталоге, функция оставляет directory отключать отображение. Имя файла имеет слишком большую длину, каталогов и расширение удаляются. Если имя файла слишком длинное, отображаемое имя равно пустой строке, если `bAtLeastName` имеет ненулевое значение.  
  
##  <a name="getsize"></a>CRecentFileList::GetSize  
 Получает число файлов в списке наиболее часто Используемых файлов.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число файлов в текущем последних использованных списка файлов (MRU).  
  
##  <a name="operator_at"></a>[CRecentFileList::operator]  
 Перегруженные нижнего индекса ( `[]`) оператор возвращает один `CString` указан, отсчитываемый от нуля индекс в `nIndex`.  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс `CString` в наборе `CString`s.  
  
##  <a name="readlist"></a>CRecentFileList::ReadList  
 Считывает последние использовавшиеся списка файлов (MRU) в реестре или приложения. INI-файл.  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>CRecentFileList::Remove  
 Удаляет файл из списка наиболее часто Используемых файлов.  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс файл удаляется из списка недавно использованных файлов (MRU).  
  
##  <a name="updatemenu"></a>CRecentFileList::UpdateMenu  
 Обновляет отображение меню списка Использованных файлов.  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта для недавно использовавшихся меню списка файлов (MRU).  
  
##  <a name="writelist"></a>CRecentFileList::WriteList  
 Записывает последние использовавшиеся списка файлов (MRU) в реестре или приложения. INI-файл.  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




