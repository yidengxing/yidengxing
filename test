//页面置换算法
import random
def FIFO(page,arr):
    print("FIFO页面置换过程为:" )
    result=[]
    loss_page=0
    sum=0
    for item in arr:
        if len(result)==page:
            for j in range(sum, len(arr)):
                if arr[j] in result:
                    print("不缺页\t第%i页"%j,end="")
                    # print("第%i页"%j,end="")
                    print(result)
                else:
                    del result[0]
                    result.append(arr[j])
                    loss_page += 1
                    print("第%i页" % j,end="")
                    print(result)
            break
        elif item in result:
            print("不缺页\t第%i页"% sum,end="")
            print(result)
            sum+=1
        else:
            result.append(item)
            loss_page+=1
            print("第%i页" % sum,end="")
            print(result)
            sum+=1

    result_page=float((loss_page)/len(arr))
    print("FIFO缺页率为：%.2f"%result_page)

def LRU(page,arr):
    print(arr)
    print("LRU页面置换过程为:")
    result = []
    loss_page = 0
    sum = 0
    for item in arr:
        if len(result)==page:
            for j in range(sum, len(arr)):
                if arr[j] in result:
                    print("不缺页\t第%i页"% j, end="")
                    p=result[result.index(arr[j])]
                    del result[result.index(arr[j])]
                    result.insert(0,p)
                    print(result)
                else:
                    del result[-1]
                    result.insert(0,arr[j])
                    loss_page += 1
                    print("第%i页" % j, end="")
                    print(result)
            break
        elif item in result:
            print("不缺页")
            p = result[result.index(item)]
            del result[result.index(item)]
            result.insert(0, p)
            print("第%i页" % sum, end="")
            print(result)
            sum+=1
        else:
            result.insert(0,item)
            loss_page+=1
            print("第%i页" % sum, end="")
            print(result)
            sum+=1
    result_page=float((loss_page)/len(arr))
    print("LRU缺页率为：%.2f"%result_page)

def bidui(param, result):
    list_1 = {}
    for item in param:
        list_1[item]=param.index(item)
    for i in result:
        if i not in list_1.keys():
            return i
        else:
           pass
    return list(list_1.keys())[list(list_1.values()).index(max(list_1.values()))]
def OPT(page,arr):
    print("OPT页面置换过程为:")
    result = []
    loss_page = 0
    sum = 0
    for item in arr:
        if len(result)==page:
            for j in range(sum, len(arr)):
                if arr[j] in result:
                    print("不缺页\t第%i页"% j, end="")
                    p = result[result.index(arr[j])]
                    del result[result.index(arr[j])]
                    result.insert(0, p)
                    print(result)
                else:
                    result_number=bidui(arr[j:len(arr)],result)
                    for o in result:
                        if result_number==o:
                            result.remove(o)
                            result.append(arr[j])
                            loss_page += 1
                            print("第%i页" % j, end="")
                            print(result)
            break
        elif item in result:
            print("不缺页\t第%i页"% sum, end="")
            print(result)
            sum+=1
        else:
            result.append(item)
            loss_page+=1
            print("第%i页" % sum, end="")
            print(result)
            sum+=1

    result_page=float((loss_page)/len(arr))
    print("OPT缺页率为：%.2f"%result_page)


if __name__ == '__main__':
    arr=[]
    number1=int(input("请输入页面流长度"))
    for i in range(number1):
         arr.append(random.randint(1,number1))
    print(arr)

    number=int(input("请输入主存块数"))
    print("选择<1>应用 FIFO 算法")
    print("选择<2>应用 LRU 算法")
    print("选择<3>应用 OPT 算法")
    c1 = int(input("选择算法："))
    if c1 == 1:
        FIFO(number,arr)
    elif c1 == 2:
        LRU(number, arr)
    elif c1 == 3:
        OPT(number,arr)
