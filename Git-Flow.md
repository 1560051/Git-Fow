GIT - Flow
=========
Git-flow là một tập các thao tác mở rộng của git nhằm cung cấp các thao tác repository (kho mã nguồn) ở mức cao dựa trên mô hình phân nhánh của Vincent Driessen.

Init
---------
-Để tạo 1 `git-flow` ta dùng câu lệnh: `git flow init`
Sẽ tạo ra các branch: master branch, develop branch, release branch, hotfix 

Feature
---------
- Để phát triển tính năng ta phải bắt đầu từ nhánh develop.
- Câu lệnh tạo feature branch: `git flow feature start feature-name`
- Feature branch được tạo từ nhánh develop và sẽ tự chuyển sang nhánh này sau khi thực hiện câu lệnh

Pushlish Feature
######
- Khi bạn làm việc với những người khác trên cùng một tính năng, bạn sẽ cần công bố phần mã nguồn của bạn cho tính năng đó lên remote để những người khác có thể cập nhập được.
- `git flow feature pull REMOTE_NAME MYFEATURE` : để pull mã nguồn của tính năng được cập nhập bởi những thành viên khác.
Finish Feature
#########
- Sau khi phát triển xong một tính năng, lệnh kết thúc tính năng `git flow feature finish feature-name`
- Khi thực hiện câu lệnh thì feature đó sẽ được merge vào nhánh develop sau đó sẽ chuyển sang nhánh develop
Release
-----------
- Release branches được sử dụng để chuẩn bị cho release bản production mới. Tất cả các công việc cuối cùng trước khi release sẽ được thực hiện ở đây, ngoài ra còn để fix nốt các bugs lẻ tẻ, chuẩn bị meta-data (version number, build dates, etc..). Nhờ việc tách nhánh ra khỏi develop, chúng ta có thể tiếp tục phát triển các features cho đợt release khác một cách bình thường.


- Kết thúc release branch
########

Khi source code trên release branch sẵn sàng để release, đầu tiên, phải merge vào master, sau đó phải đc merge lại vào develop để những lần release sau cũng chứa những thay đổi ở lần này.