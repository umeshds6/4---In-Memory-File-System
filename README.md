# 4---In-Memory-File-System


src_folder = "C:\\TestRuby"
dest_folder = "C:\\TestRubyDest"
from_file = "C:\\TestRuby\\test.txt"
to_file = "C:\\TestRuby\\dest_test.txt"

if File.exists?(src_folder) == true
  File.open(from_file, 'w') do |text|
    text.puts "Created by Umesh"
  end
else
  Dir.mkdir(src_folder)
  File.open(from_file, 'w') do |text|
    text.puts "Created by Umesh"
  end
end

in_file = open(from_file)
in_data = in_file.read
out_file = open(to_file, 'w')
out_file.write(in_data)
out_file.write("Congratulations")
in_file.close
out_file.close
FileUtils.copy_entry src_folder, dest_folder

