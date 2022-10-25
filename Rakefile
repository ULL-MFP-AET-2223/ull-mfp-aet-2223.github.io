desc "Publicar en GitHub los apuntes de AET"
task :default do
  sh "git ci -am 'AET 2022/2023' && git push -u origin main && git push -u aet2223 main"
end

desc "Actualizar students y Publicar"
task :publish => [ :students ] do
  sh "git ci -am 'AET 2022/2023' && git push -u origin main && git push -u aet2223 main"
end

desc "update AET teams (all teams"
task :teams do
  sh ". ./get-teams.sh > _data/teams.json"
end

desc "update AET students (teams of one)"
task :students do
  sh ". ./get-teams.sh > _data/students.json"
end

desc "serve locally"
task :serve do
  sh "bundle exec jekyll serve --future --watch --drafts --host 0.0.0.0 --port 8084"
end

desc "stop the server"
task :stop do
  sh "ps aux |grep jekyll |awk '{print $2}' | xargs kill -9"
end

desc "build and watch locally"
task :bw do
  sh "bundle exec jekyll build --future --drafts --watch"
end

task :updatebundler do
  sh "bundle update --bundler"
end

# docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" --env JEKYLL_ENV=development -p 4000:4000 jekyll/jekyll jekyll serve
# https://dev.to/michael/compile-a-jekyll-project-without-installing-jekyll-or-ruby-by-using-docker-4184
# docker run --rm 
# --volume="$PWD:/srv/jekyll" 
# --volume="$PWD/vendor/bundle:/usr/local/bundle" 
# --env JEKYLL_ENV=development -p 4000:4000 
# jekyll/jekyll:3.8 jekyll serve
task :docker do
  # sh 'docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" --env JEKYLL_ENV=development -p 4000:4000 jekyll/jekyll:3.8 jekyll serve'
  sh 'docker compose up' 
end
