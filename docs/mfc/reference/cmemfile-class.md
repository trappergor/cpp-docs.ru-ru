---
title: Класс CMemFile | Документация Майкрософт
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
ms.openlocfilehash: 3584568196fbccc9bab33ea3b51e876e174cbd18
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336598"
---
# <a name="cmemfile-class"></a>Класс CMemFile
[CFile](../../mfc/reference/cfile-class.md)-производный класс, поддерживающий файлы памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|Создает объект памяти файла.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|Присоединяет блок памяти, чтобы `CMemFile`.|  
|[CMemFile::Detach](#detach)|Отсоединяет блок памяти из `CMemFile` и возвращает указатель на блок памяти, отсоединена.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|Переопределение, чтобы изменить поведение распределения памяти.|  
|[CMemFile::Free](#free)|Переопределение для изменения поведения освобождение памяти.|  
|[CMemFile::GrowFile](#growfile)|Переопределение для изменения поведения при увеличении файла.|  
|[CMemFile::Memcpy](#memcpy)|Переопределение для изменения поведения копирования памяти при чтении и записи файлов.|  
|[CMemFile::Realloc](#realloc)|Переопределение для изменения поведения перераспределение памяти.|  
  
## <a name="remarks"></a>Примечания  
 Эти файлы памяти ведут себя как файлы на диске, за исключением того, что файл хранится в ОЗУ, а не на диске. Файл памяти полезно для обеспечивается быстродействие временного хранилища или для передачи необработанные байты или сериализованных объектов между независимые процессы.  
  
 `CMemFile` объекты можно автоматически назначать собственной памятью или присоединить собственный блок памяти, который `CMemFile` путем вызова метода [Attach](#attach). В любом случае память для растущих файле памяти автоматически выделяется `nGrowBytes`-размера с шагом, если `nGrowBytes` не равно нулю.  
  
 Блок памяти будет автоматически удалено после уничтожения `CMemFile` объекта, если объем памяти, первоначально был выделен функцией `CMemFile` объект; в противном случае вы несете ответственность за освобождение памяти, присоединенный к объекту.  
  
 Вы можете открыть блок памяти через указателю при отсоединении его из `CMemFile` путем вызова метода [отсоединения](#detach).  
  
 Наиболее распространенное использование `CMemFile` заключается в создании `CMemFile` и используйте его, вызвав [CFile](../../mfc/reference/cfile-class.md) функций-членов. Обратите внимание, что создание `CMemFile` автоматически открывает его: не следует вызывать [CFile::Open](../../mfc/reference/cfile-class.md#open), который используется только для файлов на диске. Так как `CMemFile` не использует файл на диске, член данных `CFile::m_hFile` не используется.  
  
 `CFile` Функции-члены [дублировать](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), и [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) не реализованы для `CMemFile`. При вызове этих функций для `CMemFile` объекта, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile` с помощью функций библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md), и [бесплатный](../../c-runtime-library/reference/free.md) для размещения, повторного выделения и освобождения памяти и встроенная [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) блок копирования памяти при чтении и записи. Если вы хотите изменить это поведение или поведение при `CMemFile` роста файла, собственный производный класс от `CMemFile` и переопределите соответствующие функции.  
  
 Дополнительные сведения о `CMemFile`, см. в статьях [файлы в MFC](../../mfc/files-in-mfc.md) и [памяти управления (MFC)](../../mfc/memory-management.md) и см. в разделе [обработка файлов](../../c-runtime-library/file-handling.md) в *во время выполнения Справочник по библиотеке*.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="alloc"></a>  CMemFile::Alloc  
 Эта функция вызывается `CMemFile` функций-членов.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 *nBytes*  
 Число байтов памяти, который необходимо выделить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, который был выделен, или значение NULL, если не удалось выполнить выделение.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для реализации пользовательских области памяти. Если вы переопределите эту функцию, можно переопределить [бесплатный](#free) и [Realloc](#realloc) также.  
  
 Реализация по умолчанию использует функцию библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md) для выделения памяти.  
  
##  <a name="attach"></a>  CMemFile::Attach  
 Вызывайте эту функцию для присоединения блок памяти, чтобы `CMemFile`.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *lpBuffer*  
 Указатель на буфер, должны быть присоединены к `CMemFile`.  
  
 *nBufferSize*  
 Целое число, указывающее размер буфера в байтах.  
  
 *nGrowBytes*  
 Приращение выделения памяти в байтах.  
  
### <a name="remarks"></a>Примечания  
 В результате `CMemFile` для использования в качестве файла памяти блок памяти.  
  
 Если *nGrowBytes* равно 0, `CMemFile` установит длина файла *nBufferSize*. Это означает, что данные в блок памяти, прежде чем он был подключен к `CMemFile` будет использоваться в качестве файла. Не удается возросла памяти файлы, созданные таким образом.  
  
 Так как файл не может быть явном, не следует вызывать `CMemFile` для роста файла. Например, не вызывайте `CMemFile` переопределениям [CFile:Write](../../mfc/reference/cfile-class.md#write) к записи за пределами или не вызывайте [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) с длиной более *nBufferSize*.  
  
 Если *nGrowBytes* больше 0, `CMemFile` будет игнорировать содержимое блока памяти, к ранее. Вам придется записать содержимое файла памяти с нуля с помощью `CMemFile` переопределения `CFile::Write`. При попытке записи за пределами файла, или увеличьте размер файла путем вызова `CMemFile` переопределения `CFile::SetLength`, `CMemFile` будет увеличиваться выделение памяти с шагом *nGrowBytes*. Увеличение размера выделенной памяти завершится ошибкой, если блок памяти, указываемые для `Attach` не был выделен с помощью метода, совместимый с [Alloc](#alloc). Для обеспечения совместимости с реализацией по умолчанию `Alloc`, необходимо выделить память с помощью функции библиотеки времени выполнения [malloc](../../c-runtime-library/reference/malloc.md) или [calloc](../../c-runtime-library/reference/calloc.md).  
  
##  <a name="cmemfile"></a>  CMemFile::CMemFile  
 Первая перегрузка открывает файл пустой памяти.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *nGrowBytes*  
 Приращение выделения памяти в байтах.  
  
 *lpBuffe*r  
 Указатель на буфер, получающий сведения от размера *nBufferSize*.  
  
 *nBufferSize*  
 Целое число, указывающее размер буфера файла в байтах.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что файл открыт с помощью конструктора, и что не следует вызывать [CFile::Open](../../mfc/reference/cfile-class.md#open).  
  
 Вторая перегрузка функционирует так же, как в том случае, если вы использовали первый конструктор и сразу же вызывается [Attach](#attach) с теми же параметрами. Подробные сведения см. в разделе `Attach`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>  CMemFile::Detach  
 Вызывайте эту функцию, чтобы получить указатель на блок памяти, используемый `CMemFile`.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, который содержит содержимое файла памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции также закрывает `CMemFile`. Можно легко повторно подключить блок памяти, который `CMemFile` путем вызова [Attach](#attach). Если вы хотите заново присоединить файл и использовать данные в нем, необходимо вызвать [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) для получения длины файла перед вызовом `Detach`. Обратите внимание, что при подключении блок памяти, чтобы `CMemFile` таким образом, вы можете использовать его данные ( `nGrowBytes` == 0), то нельзя, до которого может увеличиваться файл памяти.  
  
##  <a name="free"></a>  CMemFile::Free  
 Эта функция вызывается `CMemFile` функций-членов.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>Параметры  
 *lpMem*  
 Указатель на память будет отменено позже.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для освобождения памяти для настраиваемой реализации. Если вы переопределите эту функцию, можно переопределить [Alloc](#alloc) и [Realloc](#realloc) также.  
  
##  <a name="growfile"></a>  CMemFile::GrowFile  
 Эта функция вызывается в нескольких `CMemFile` функций-членов.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>Параметры  
 *dwNewLen*  
 Новый размер файла памяти.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите изменить его можно переопределить как `CMemFile` роста его файл. По умолчанию реализация вызывает [Realloc](#realloc) расти существующий блок (или [Alloc](#alloc) для создания блока памяти), выделение памяти кратно `nGrowBytes` значение, указанное в конструкторе или [Attach](#attach) вызова.  
  
##  <a name="memcpy"></a>  CMemFile::Memcpy  
 Эта функция вызывается `CMemFile` переопределениям [CFile::Read](../../mfc/reference/cfile-class.md#read) и [CFile::Write](../../mfc/reference/cfile-class.md#write) для передачи данных и обратно в файл.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 *lpMemTarget*  
 Указатель на блок памяти, в которую будут скопированы память источника.  
  
 *lpMemSource*  
 Указатель на блок памяти источника.  
  
 *nBytes*  
 Число байтов для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия *lpMemTarget*.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите изменить способ, `CMemFile` эти копии памяти.  
  
##  <a name="realloc"></a>  CMemFile::Realloc  
 Эта функция вызывается `CMemFile` функций-членов.  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 *lpMem*  
 Указатель на блок памяти перераспределить.  
  
 *nBytes*  
 Новый размер блока памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на блок памяти, перераспределить (и возможно переместить), или значение NULL, если не удалось выполнить перераспределение.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для перераспределения памяти для настраиваемой реализации. Если вы переопределите эту функцию, можно переопределить [Alloc](#alloc) и [бесплатный](#free) также.  
  
## <a name="see-also"></a>См. также  
 [Класс CFile](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



