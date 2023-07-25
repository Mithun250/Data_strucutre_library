class library:
  def __init__(self,data):
    self.book_list=data
    
  def show(self):
    print(self.book_list)

  def lend_book(self,book):
    if book in self.book_list:
      self.book_list.remove(book)
      print("Book is issued ",book)
      return True

    else:
      print("there is no such a book")
      return False
    
  def cust_return_book(self,data):
    self.book_list.append(returned_book)

class customer:
  def __init__(self):
    self.cust_book=[]

  def add_book(self,book_name):
    self.cust_book.append(requested_book)

  def show(self):
    print(self.cust_book)

  def req_book(self):
    print("Enter the Book")
    self.book=input()
    return self.book
  
  def ret_book(self):
    print("Enter the book you want to return")
    self.book=input()
    return self.book
  
  def no_return_book(self,book):
    if book in self.cust_book:
      self.cust_book.remove(book)
      print("Your book is successfully returned",book)
      return True

    else:
      print("the book is wrong")



lib_chennai=library(["book1","book2","book3","book4","book5","book2",])
mithun=customer()

while True:
  print("------------------------------------------------------------------------")
  print("select the option bellow")
  print("1 - Show the list of books \n2 - Lend a book \n3 Customer borrowed books  \n4 Customer return the book \n0 - exit")
  option =int(input("Enter the number : "))
  print("------------------------------------------------------------------------")

  if option ==1:
    lib_chennai.show()

  elif option ==2:
    requested_book=mithun.req_book()
    status=lib_chennai.lend_book(requested_book)
    if status==True:
      mithun.add_book(requested_book)

  elif option==3:
    mithun.show()

  elif option==4:
    returned_book=mithun.ret_book()
    status=mithun.no_return_book(returned_book)
    if status==True:
      lib_chennai.cust_return_book(returned_book)

  elif option ==0:
    break


