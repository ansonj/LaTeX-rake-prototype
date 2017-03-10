# Delete this line or set to nil if not interested
$target_length = 10..15

desc 'Default task (process with BibTeX)'
task default: [:bibtex]

desc 'Open output pdf'
task :open do
  func_open
end

desc 'Process with BibTeX'
task :bibtex do
  func_run_dry
  func_run_bibtex
  func_run_dry
  func_run_create
  func_open
  func_print_target
end

desc 'Process, but skip BibTeX'
task :nobib do
  func_run_dry
  func_run_create
  func_open
  func_print_target
end

desc 'Quick recreate+open pdf'
task :quick do
  func_run_create
  func_open
end

desc 'Print target length'
task :len do
  func_print_target
end

def func_run_dry
  sh 'pdflatex -draftmode -halt-on-error master.tex'
end

def func_run_create
  sh 'pdflatex -halt-on-error master.tex'
end

def func_run_bibtex
  sh 'bibtex master'
end

def func_open
  sh 'open ./master.pdf'
end

def func_print_target
  return if $target_length.nil?
  puts "Target length is #{$target_length.first}-#{$target_length.last} pages."
end
