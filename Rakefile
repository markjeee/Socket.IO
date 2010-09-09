SOCKET_IO_FILES = [
                   'io.js',
                   'util.js',
                   'transport.js',
                   'transports/xhr.js',
                   'transports/websocket.js',
                   'transports/flashsocket.js',
                   'transports/htmlfile.js',
                   'transports/xhr-multipart.js',
                   'transports/xhr-polling.js',
                   'transports/jsonp-polling.js',
                   'socket.js',
                   'vendor/web-socket-js/swfobject.js',
                   'vendor/web-socket-js/FABridge.js',
                   'vendor/web-socket-js/web_socket.js'
                  ]

SOCKET_IO_ROOT_PATH = File.expand_path(File.dirname(__FILE__))
SOCKET_IO_OUTPUT_FILE = 'socket.io.js'

task :build do
  puts "Reading files"
  content = ""
  SOCKET_IO_FILES.each do |f|
    path = File.join(SOCKET_IO_ROOT_PATH, 'lib', f)
    if File.exists?(path)
      puts "  + #{f}"
      content += "/********\n"
      content += "  Built from: #{f}\n"
      content += "*********\n"
      content += File.read(path) + "\n\n"
    end
  end

  puts "\n"

  output_file = SOCKET_IO_OUTPUT_FILE
  puts "Writing #{output_file}"

  output_path = File.join(SOCKET_IO_ROOT_PATH, output_file)
  File.open(output_path, "w") do |f|
    f.write(content)
  end

  puts "...done."
end

task :default => :build
