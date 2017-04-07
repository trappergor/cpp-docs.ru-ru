---
title: "Класс CMemFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
dev_langs:
- C++
helpviewer_keywords:
- memory files
- CMemFile class
- temporary files, memory files
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
caps.latest.revision: 21
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
ms.openlocfilehash: 9851e050b05ac129e5e498c7ea99dfedddc79e54
ms.lasthandoff: 02/24/2017

---
# <a name="cmemfile-class"></a>Класс CMemFile
[CFile](../../mfc/reference/cfile-class.md)-производного класса, который поддерживает файлы памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|Создает объект памяти файла.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|Присоединяет блока памяти `CMemFile`.|  
|[CMemFile::Detach](#detach)|Отсоединяет блока памяти из `CMemFile` и возвращает указатель на блок памяти отсоединена.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|Переопределение, чтобы изменить поведение распределения памяти.|  
|[CMemFile::Free](#free)|Переопределение для изменения поведения при освобождении памяти.|  
|[CMemFile::GrowFile](#growfile)|Переопределение для изменения поведения при увеличении объема файла.|  
|[CMemFile::Memcpy](#memcpy)|Переопределение для изменения поведения копирования памяти при чтении и записи файлов.|  
|[CMemFile::Realloc](#realloc)|Переопределение для изменения поведения перераспределение памяти.|  
  
## <a name="remarks"></a>Примечания  
 Эти файлы памяти ведут себя как дисковые файлы, за исключением того, что файл хранится в оперативной памяти, а не на диске. В памяти файла используется для быстрого временного хранения или передачи необработанных байтов или сериализуемые объекты между процессами независимо.  
  
 `CMemFile`объекты можно автоматически распределять собственной памятью или можно присоединить собственный блок памяти, который `CMemFile` путем вызова метода [присоединить](#attach). В любом случае выделяется память для автоматического увеличения размера файла памяти `nGrowBytes`-размера с шагом, если `nGrowBytes` не равен нулю.  
  
 Блок памяти будет автоматически удалено после уничтожения `CMemFile` объекта, если память изначально была выделена путем `CMemFile` объекта; в противном случае, вы несете ответственность за освобождение памяти, присоединенный к объекту.  
  
 Блок памяти доступен в указатель, предоставленный при отсоединении от `CMemFile` путем вызова метода [отсоединения](#detach).  
  
 Наиболее распространенное использование `CMemFile` заключается в создании `CMemFile` и использовать его, вызвав [CFile](../../mfc/reference/cfile-class.md) функции-члены. Обратите внимание, что создание `CMemFile` автоматически открывает: не следует вызывать [CFile::Open](../../mfc/reference/cfile-class.md#open), который используется только файлов на диске. Поскольку `CMemFile` не использует файл диска, член данных `CFile::m_hFile` не используется.  
  
 `CFile` Функции-члены [дублировать](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), и [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) не реализована для `CMemFile`. При вызове этих функций для `CMemFile` объект, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile`использует функции библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md), [перераспределения](../../c-runtime-library/reference/realloc.md), и [свободного](../../c-runtime-library/reference/free.md) для выделения, перераспределения и освобождения памяти и встроенная [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) блок копирования памяти при чтении и записи. Если вы хотите изменить это поведение или поведение при `CMemFile` роста файл, создать собственный производный класс от `CMemFile` и переопределить соответствующие функции.  
  
 Дополнительные сведения о `CMemFile`, см. в статьях [файлы в MFC](../../mfc/files-in-mfc.md) и [управления памяти (MFC)](../../mfc/memory-management.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="alloc"></a>CMemFile::Alloc  
 Эта функция вызывается `CMemFile` функции-члены.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Число байтов памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, которая была выделена или **NULL** случае сбоя выделения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы реализовать пользовательские области памяти. Если переопределить эту функцию, может потребоваться переопределить [Free](#free) и [Realloc](#realloc) также.  
  
 Реализация по умолчанию использует функции библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md) для выделения памяти.  
  
##  <a name="attach"></a>CMemFile::Attach  
 Эта функция вызывается для присоединения блока памяти `CMemFile`.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuffer`  
 Указатель на буфер, должны быть присоединены к `CMemFile`.  
  
 `nBufferSize`  
 Целое число, указывающее размер буфера в байтах.  
  
 `nGrowBytes`  
 Шаг выделения памяти в байтах.  
  
### <a name="remarks"></a>Примечания  
 В результате `CMemFile` для использования в качестве файла памяти блок памяти.  
  
 Если `nGrowBytes` равно 0, `CMemFile` будет присвоено длина файла `nBufferSize`. Это означает, что данные в блоке памяти, прежде чем он был присоединен к `CMemFile` будет использоваться как файл. Не удается увеличил создается таким образом файлы памяти.  
  
 Поскольку файл не может быть установка, не следует вызывать `CMemFile` для роста файла. Например, не вызвать `CMemFile` переопределений [CFile:Write](../../mfc/reference/cfile-class.md#write) для записи за пределами или не вызвать [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) с длиной более `nBufferSize`.  
  
 Если `nGrowBytes` больше, чем 0, `CMemFile` будет игнорировать содержимое блока памяти была присоединена. Вам придется записать содержимое в файл памяти с нуля с помощью `CMemFile` переопределение `CFile::Write`. При попытке записи за пределами файла или расширить файл путем вызова `CMemFile` переопределение `CFile::SetLength`, `CMemFile` будет расти выделения памяти с шагом `nGrowBytes`. Увеличение выделения памяти завершится ошибкой, если блок памяти, которая передается **присоединить** не был выделен с помощью метода, совместимый с [Alloc](#alloc). Для обеспечения совместимости с реализацией по умолчанию `Alloc`, необходимо выделить память с помощью функции библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md) или [calloc](../../c-runtime-library/reference/calloc.md).  
  
##  <a name="cmemfile"></a>CMemFile::CMemFile  
 Первая перегрузка открывает файл пустой памяти.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nGrowBytes`  
 Шаг выделения памяти в байтах.  
  
 *lpBuffe*r  
 Указатель на буфер, получающий сведения размера `nBufferSize`.  
  
 `nBufferSize`  
 Целое число, указывающее размер буфера файла в байтах.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что файл открыт в конструкторе, и что не следует вызывать [CFile::Open](../../mfc/reference/cfile-class.md#open).  
  
 Вторая перегрузка функционирует так же, как если бы используется первый конструктор и сразу же вызывается [присоединить](#attach) с теми же параметрами. В разделе **присоединить** подробные сведения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#36;](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>CMemFile::Detach  
 Эта функция вызывается для получения указателя на блок памяти, используемый `CMemFile`.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, содержащий содержимое в файл памяти.  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функции также закрывает `CMemFile`. Можно легко повторно подключить блок памяти, который `CMemFile` путем вызова [присоединить](#attach). Если вы хотите повторно вложить файл и использовать данные, необходимо вызвать [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) получить длину файла перед вызовом метода **отсоединения**. Обратите внимание, что при присоединении блок памяти, который `CMemFile` , чтобы вы могли использовать свои данные ( `nGrowBytes` == 0), то вы не сможете расти в файл памяти.  
  
##  <a name="free"></a>CMemFile::Free  
 Эта функция вызывается `CMemFile` функции-члены.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMem`  
 Указатель на память освободить *.*  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для освобождения памяти для настраиваемой реализации. Если переопределить эту функцию, может потребоваться переопределить [Alloc](#alloc) и [Realloc](#realloc) также.  
  
##  <a name="growfile"></a>CMemFile::GrowFile  
 Эта функция вызывается в нескольких `CMemFile` функции-члены.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>Параметры  
 `dwNewLen`  
 Новый размер в файл памяти.  
  
### <a name="remarks"></a>Примечания  
 Его можно изменить, если требуется изменить как `CMemFile` роста его файл. Реализация по умолчанию вызывает [перераспределения](#realloc) расти существующий блок (или [Alloc](#alloc) для создания блока памяти), выделение памяти кратно `nGrowBytes` значения, указанного в конструкторе или [присоединить](#attach) вызова.  
  
##  <a name="memcpy"></a>CMemFile::Memcpy  
 Эта функция вызывается `CMemFile` переопределений [CFile::Read](../../mfc/reference/cfile-class.md#read) и [CFile::Write](../../mfc/reference/cfile-class.md#write) для обмена данными в файл памяти.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMemTarget`  
 Указатель на блок памяти, в который будут копироваться памяти источника.  
  
 `lpMemSource`  
 Указатель на блок памяти источника.  
  
 `nBytes`  
 Число байтов для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия `lpMemTarget`.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию, если вы хотите изменить способ, `CMemFile` эти копии памяти.  
  
##  <a name="realloc"></a>CMemFile::Realloc  
 Эта функция вызывается `CMemFile` функции-члены.  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMem`  
 Указатель на блок памяти, чтобы перераспределить.  
  
 `nBytes`  
 Новый размер блока памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, повторно (и возможно перемещена), или **NULL** Если перераспределение не удалось.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для реализации перераспределение памяти для настраиваемой. Если переопределить эту функцию, может потребоваться переопределить [Alloc](#alloc) и [Free](#free) также.  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




