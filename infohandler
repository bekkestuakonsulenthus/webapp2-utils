import webapp2
import json

class MainHandler(webapp2.RequestHandler):
    def get(self):
      self.response.out.write('Hello world')
    
class InfoHandler(webapp2.RequestHandler):
    def get(self):
        http_methods = ['get', 'post', 'put', 'patch', 'delete', 'options']
        pretty_routes = []
        for route in routes:
            methods = []
            obj = {
                'route' : route[0],
                'route_methods': methods
            }

            handler = route[1].__dict__
            for key in handler.keys():
                if key.lower() in http_methods:
                    methods.append(key.lower())

            pretty_routes.append(obj)
        self.response.out.write(json.dumps(pretty_routes, sort_keys=True))
        return
       
routes = [
    (r'/', MainHandler),
    (r'/api/v1/info', InfoHandler)
]

app = webapp2.WSGIApplication(routes, debug=True)
