---
title: Класс CMemFile | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81421c99623fd3ab0abde20b479ec1ba91c3f936
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmemfile-class"></a>Класс CMemFile
[CFile](../../mfc/reference/cfile-class.md)-производный класс, поддерживающий файлы памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|Создает объект памяти файла.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|Присоединяет блока памяти `CMemFile`.|  
|[CMemFile::Detach](#detach)|Отсоединяет блок памяти из `CMemFile` и возвращает указатель на блок памяти отсоединена.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|Переопределите, чтобы изменить поведение распределения памяти.|  
|[CMemFile::Free](#free)|Переопределение для изменения поведения освобождение памяти.|  
|[CMemFile::GrowFile](#growfile)|Переопределение для изменения поведения при увеличении файла.|  
|[CMemFile::Memcpy](#memcpy)|Переопределите, чтобы изменить поведение копирования памяти при чтении и записи файлов.|  
|[CMemFile::Realloc](#realloc)|Переопределение для изменения поведения повторного выделения памяти.|  
  
## <a name="remarks"></a>Примечания  
 Эти файлы памяти ведут себя как дисковые файлы, за исключением того, что файл хранится в оперативной памяти, а не на диске. Файл памяти полезен для быстрого временного хранилища для передачи необработанные байты или сериализованных объектов между независимыми процессов.  
  
 `CMemFile` объекты можно автоматически выделить собственные память или присоединить собственные блок памяти, который `CMemFile` путем вызова метода [присоединение](#attach). В любом случае память автоматически ростом файла памяти выделяется `nGrowBytes`-размера с шагом, если `nGrowBytes` не равно нулю.  
  
 Блок памяти будет автоматически удалено после удаления `CMemFile` объекта, если объем памяти был первоначально занимаемый `CMemFile` объекта; в противном случае вы несете ответственность за освобождение памяти, подключенной к объекту.  
  
 Вы можете открыть блок памяти через указателю при отсоединении от `CMemFile` путем вызова метода [отсоединения](#detach).  
  
 Чаще всего используют `CMemFile` заключается в создании `CMemFile` и используйте его, вызвав [CFile](../../mfc/reference/cfile-class.md) функции-члены. Обратите внимание, что создание `CMemFile` автоматически открывает: не следует вызывать [CFile::Open](../../mfc/reference/cfile-class.md#open), который используется только файлов на диске. Поскольку `CMemFile` не использует файл на диске, элемент данных `CFile::m_hFile` не используется.  
  
 `CFile` Функции-члены [дублировать](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), и [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) не реализован для `CMemFile`. При вызове этих функций для `CMemFile` объекта, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile` с помощью функций библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md), и [свободного](../../c-runtime-library/reference/free.md) для выделения, перераспределения и освобождения памяти; и встроенную функцию [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) в памяти копию блока при чтении и записи. Если вы хотите изменить это поведение или поведение при `CMemFile` увеличения размера файла, создайте производный класс из `CMemFile` и заменяют соответствующие функции.  
  
 Дополнительные сведения о `CMemFile`, см. в статьях [файлы в MFC](../../mfc/files-in-mfc.md) и [управления памяти (MFC)](../../mfc/memory-management.md) и в разделе [обработка файлов](../../c-runtime-library/file-handling.md) в *во время выполнения Справочник по библиотеке*.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="alloc"></a>  CMemFile::Alloc  
 Эта функция вызывается `CMemFile` функции-члены.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Число байтов памяти, которые нужно выделить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, которая была выделена или **NULL** Если сбой при выделении.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для реализации пользовательской области памяти. Если эта функция, возможно, имеет смысл переопределить [Free](#free) и [Realloc](#realloc) также.  
  
 Реализация по умолчанию с помощью функции библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md) для выделения памяти.  
  
##  <a name="attach"></a>  CMemFile::Attach  
 Эта функция вызывается для присоединения блока памяти `CMemFile`.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuffer`  
 Указатель на буфер для присоединения к `CMemFile`.  
  
 `nBufferSize`  
 Целое число, указывающее размер буфера в байтах.  
  
 `nGrowBytes`  
 Приращение выделения памяти в байтах.  
  
### <a name="remarks"></a>Примечания  
 В результате `CMemFile` для использования в качестве файла памяти блок памяти.  
  
 Если `nGrowBytes` равно 0, `CMemFile` установит длина файла `nBufferSize`. Это означает, что данные в блок памяти, прежде чем он был присоединен к `CMemFile` будет использоваться как файл. Не удается увеличил создается таким образом файлы памяти.  
  
 Поскольку файл не может использоваться с, будьте внимательны и не вызвать `CMemFile` для приращения файла. Например, не вызывайте `CMemFile` переопределений [CFile:Write](../../mfc/reference/cfile-class.md#write) для записи за пределами или не вызывайте [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) с длиной более `nBufferSize`.  
  
 Если `nGrowBytes` больше, чем 0, `CMemFile` будет игнорировать содержимое блока памяти была присоединена. Вам потребуется записать содержимое файла памяти с нуля с помощью `CMemFile` переопределение `CFile::Write`. При попытке записи после конца файла или увеличение размера файла, вызвав `CMemFile` переопределение `CFile::SetLength`, `CMemFile` будет увеличиваться выделения памяти с шагом `nGrowBytes`. Увеличение выделения памяти завершится ошибкой, если блок памяти передается **присоединение** не был выделен с помощью метода, совместимый с [Alloc](#alloc). Для обеспечения совместимости с реализацией по умолчанию `Alloc`, необходимо выделить память с помощью функции библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md) или [calloc](../../c-runtime-library/reference/calloc.md).  
  
##  <a name="cmemfile"></a>  CMemFile::CMemFile  
 Первая перегрузка открывает файл пустым памяти.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nGrowBytes`  
 Приращение выделения памяти в байтах.  
  
 *lpBuffe*r  
 Указатель на буфер, который получает сведения от размера `nBufferSize`.  
  
 `nBufferSize`  
 Целое число, определяющее размер буфера файла в байтах.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что файл открыт в конструкторе, и что не следует вызывать [CFile::Open](../../mfc/reference/cfile-class.md#open).  
  
 Вторая перегрузка функционирует так же, как если бы использовать первый конструктор и сразу же вызывается [присоединение](#attach) с теми же параметрами. В разделе **присоединение** подробные сведения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>  CMemFile::Detach  
 Вызывайте эту функцию, чтобы получить указатель на блок памяти, используемый `CMemFile`.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, содержащий содержимое памяти файла.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции также закрывает `CMemFile`. Блок памяти, который можно подключить `CMemFile` путем вызова [присоединение](#attach). Если вы хотите восстановить подключение файла и использовать данные, необходимо вызвать [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) получить длину файла перед вызовом **отсоединения**. Обратите внимание, что при подключении блок памяти, который `CMemFile` , чтобы вы могли использовать его данные ( `nGrowBytes` == 0), то нельзя будет увеличиваться файл памяти.  
  
##  <a name="free"></a>  CMemFile::Free  
 Эта функция вызывается `CMemFile` функции-члены.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMem`  
 Указатель на память, чтобы быть освобождена.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для реализации освобождения памяти. Если эта функция, возможно, имеет смысл переопределить [Alloc](#alloc) и [Realloc](#realloc) также.  
  
##  <a name="growfile"></a>  CMemFile::GrowFile  
 Эта функция вызывается в нескольких `CMemFile` функции-члены.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>Параметры  
 `dwNewLen`  
 Новый размер файла памяти.  
  
### <a name="remarks"></a>Примечания  
 Его можно изменить, если вы хотите изменить как `CMemFile` увеличения размера его файла. Реализация по умолчанию вызывает [Realloc](#realloc) расти существования блока (или [Alloc](#alloc) для создания блока памяти), выделение памяти кратное `nGrowBytes` значения, указанного в конструкторе или [Присоединение](#attach) вызова.  
  
##  <a name="memcpy"></a>  CMemFile::Memcpy  
 Эта функция вызывается `CMemFile` переопределений [CFile::Read](../../mfc/reference/cfile-class.md#read) и [CFile::Write](../../mfc/reference/cfile-class.md#write) для обмена данными в файле памяти.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMemTarget`  
 Указатель на блок памяти, в которую будет копироваться памяти источника.  
  
 `lpMemSource`  
 Указатель на блок памяти источника.  
  
 `nBytes`  
 Число байтов для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия `lpMemTarget`.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию, если вы хотите изменить способ, `CMemFile` эти копии памяти.  
  
##  <a name="realloc"></a>  CMemFile::Realloc  
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
 Указатель на блок памяти, перераспределение (и возможно перемещена), или **NULL** Если перераспределение завершилось неудачей.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для реализации повторного выделения памяти. Если эта функция, возможно, имеет смысл переопределить [Alloc](#alloc) и [Free](#free) также.  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



