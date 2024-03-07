import random
start = 0
round = 0
turn = random.randint(1,2)
module = True
qtrong=[1,5,9,13,17,21,25,29]

def check():
        if (start == 30):
            return False
        else:
            return True
def ktra(choose): 
            if max(choose) > 30:
                print("lỗi vui lòng nhập lại số bé hơn hoac bang 30")
                p_choose()
            else:
                if len(choose)==1:
                    if choose[0] == (start +1):
                        start = choose[0]
                    else:
                        print("lỗi lựa chọn số phải theo thứ tự")
                    p_choose()
                elif len(choose)==2:
                    if (choose[0]==start +1 choose[1]== start +2)
                       start = choose[1]
                   else:
                       print("lỗi lựa chọn số phải theo thứ tự")
                       p_choose()
                elif len(choose)==3:
                    if choose[0] == start+1 and choose[1]== start+2 and choose[2]== start+3:
                   start = choose[2]
                   else:
                       print("lỗi lựa chọn số phải theo thứ tự")
                       p_choose()
                      
                else:
                    print("chi nhap duoc nhieu nhat 3 so")    
                    p_choose()
        
        if (check()):
            bot_choose()
        else:
            print("nguoi choi thua, bot thang")  
            module1()          
def bot_choose():
    global start
        for i in qtrong:
            if i> start:
                if i-start ==1:
                    start +=1
                    print("bot chọn : ",start)
                elif (i-start == 2):
                    start+=2
                    print("bot chọn : ",start -1 ,start)
                elif  (i -start ==3):
                   start +=3
                   print("bot chọn : ",start -2 , start -1 ,start)
                  
               else :
                   random.randint(1,3)                  
                  
        if (check()):
            p_choose()
        else:
            print("bot da thua cuoc.nguoi choi thang")
            module1()
def p_choose():
    global module
    if module:
        choose = [int(i) for i in input("mời người chơi chọn số : ").split()]
        ktra(choose)
def module1():
    global module
    global start
    global round
    print("ấn p để chơi tiếp,q để dừng lại,h để xem hướng dẫn")
    user = input("vui lòng chọn chế độ: ")
    if user == "p" or user == "P":
        start = 0
        round = 0
        module = True
        print("số hiện tại : ",start)
        run()
    elif user =="q" or user == "Q":
        print("product by Hyy_nguynn_17")
        print("See you later")
    elif user == "h" or user == "H":
        print("""Đối với gameplay này chúng ta sẽ chọn ra 1 số hoặc 2 hoặc 3 số liên tiếp với số trước đó đã chọn khi mak ai đếm đến 30 thfi sẽ là người thua cuộc
Ví dụ nếu máy chọn 1 thì người chơi sẽ chọn 2 hoặc 2 3 hoặc 2 3 4""")
        module1()
    else:
        print("chế độ bạn chọn hiện không có, vui lòng chọn lại")
        module1()    
def run():
    global turn
    global round
    global module
    print(turn)
    if module:
        if turn%2==1:
            p_choose()
        else:
            bot_choose()
module1()
 
